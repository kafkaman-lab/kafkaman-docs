kafkaman-cli is a command-line Collection Runner for kafkaman. It enables you to run and test a kafkaman Collection directly from the command line. It's built with extensibility in mind so that you can easily integrate it with your continuous integration servers and build systems.

kafkaman-cli maintains feature parity with kafkaman and allows you to run collections the way they are executed inside the collection runner in kafkaman.

kafkaman-cli resides in the [NPM registry](https://www.npmjs.com/package/kafkaman-cli) and on [GitHub](https://github.com/kafkamanlabs/kafkaman-cli).

[![kafkaman-cli gif](https://assets.kafkaman.com/kafkaman-docs/kafkaman-cli-running-in-terminal.gif)](https://assets.kafkaman.com/kafkaman-docs/kafkaman-cli-running-in-terminal.gif)

* [Getting Started](#getting-started)
* [Options](#options)
* [Example collection with failing tests](#example-collection-with-failing-tests)
* [Using kafkaman-cli with CI/CD](#using-kafkaman-cli-with-cicd)
* [File uploads](#file-uploads)
* [Library](#library)
* [Custom reporters](#custom-reporters)

## Getting Started

kafkaman-cli is built on Node.js. To run kafkaman-cli, make sure you have Node.js installed.

You can [download and install](https://nodejs.org/en/download/current/) Node.js on Linux, Windows, and macOS.

After you install Node.js, kafkaman-cli is just a command away. Install kafkaman-cli from npm globally on your system, which allows you to run it from anywhere.

```bash
$ npm install -g kafkaman-cli
```

The easiest way to run kafkaman-cli is to run it with a collection. You can run any collection file from your file system.

> You can [export a collection](/docs/getting-started/importing-and-exporting-data/#exporting-collections) to share as a file.

```bash
$ kafkaman-cli run mycollection.json
```

You can also pass a collection as a URL by [sharing](/docs/collaborating-in-kafkaman/sharing/#sharing-kafkaman-entities) it.

Your collection probably uses environment variables. To provide an accompanying set of [environment variables](/docs/sending-requests/managing-environments/), export the template from kafkaman and run them with the `-e` flag.

```bash
$ kafkaman-cli run https://www.kafkaman.com/collections/cb208e7e64056f5294e5 -e dev_environment.json
```

## Options

kafkaman-cli provides a rich set of options to customize a run. You can retrieve a list of options by running it with the ``-h`` flag.

```bash
$ kafkaman-cli run -h
```

### Utility

| Option | Details |
|:--|:--|
| `-h`, `--help` | Output usage information |
| `-v`, `--version` | Output the version number |

### Basic setup

| Option | Details |
|:--|:--|
| `--folder [folderName]` | Specify a single folder to run from a collection. |
| `-e`, `--environment [file\|URL]` | Specify a kafkaman environment as a JSON [file] |
| `-d`, `--iteration-data [file]` | Specify a data file to use either json or csv |
| `-g`, `--globals [file]` | Specify a kafkaman globals file as JSON [file] |
| `-n`, `--iteration-count [number]` | Define the number of iterations to run |

### Request options

| Option | Details |
|:--|:--|
| `--delay-request [number]` | Specify a delay (in ms) between requests [number] |
| `--timeout-request [number]` | Specify a request timeout (in ms) for a request |

### Misc.

| Option | Details |
|:--|:--|
| `--bail` | Stops the runner when a test case fails |
| `--silent` | Turn off terminal output |
| `--color off` | Turn off colored output (auto\|on\|off) (default: "auto")|
| `-k`, `--insecure` | Turn off strict ssl |
| `-x`, `--suppress-exit-code` | Continue running tests even after a failure, but exit with `code=0` |
| `--ignore-redirects` | Turn off automatic following of `3XX` responses |
| `--verbose` | Show detailed information of collection run and each request sent |

Use the ``-n`` option to set the number of iterations to run the collection.

```bash
$ kafkaman-cli run mycollection.json -n 10  # runs the collection 10 times
```

To provide a different set of data, such as variables for each iteration, you can use the ``-d`` to specify a JSON or CSV file.

For example, a data file such as the one shown below runs _2_ iterations, with each iteration using a set of variables.

```json
[{
    "url": "http://127.0.0.1:5000",
    "user_id": "1",
    "id": "1",
    "token_id": "123123",
},
{
    "url": "http://kafkaman-echo.com",
    "user_id": "2",
    "id": "2",
    "token_id": "899899",
}]
```

```bash
$ kafkaman-cli run mycollection.json -d data.json
```

Here's an example of the CSV file for the above set of variables:

```bash
url, user_id, id, token_id
http://127.0.0.1:5000, 1, 1, 123123123
http://kafkaman-echo.com, 2, 2, 899899
```

kafkaman-cli, by default, exits with a status code of 0 if everything runs well, such as without any exceptions.

Continuous integration tools respond to these exit codes and correspondingly pass or fail a build.

You can use `-x` or `--suppress-exit-code` to override the default exit code for the current run.

You can use the `--bail` flag to tell kafkaman-cli to halt on a test case error with a status code of 1, which can then be picked up by a CI tool or build system.

```bash
$ kafkaman-cli run kafkamanCollection.json -e environment.json --bail
```

## Example collection with failing tests

```bash
→ Status Code Test
  GET https://kafkaman-echo.com/status/404 [404 Not Found, 534B, 1551ms]
  1\. response code is 200

┌─────────────────────────┬──────────┬──────────┐
│                         │ executed │   failed │
├─────────────────────────┼──────────┼──────────┤
│              iterations │        1 │        0 │
├─────────────────────────┼──────────┼──────────┤
│                requests │        1 │        0 │
├─────────────────────────┼──────────┼──────────┤
│            test-scripts │        1 │        0 │
├─────────────────────────┼──────────┼──────────┤
│      prerequest-scripts │        0 │        0 │
├─────────────────────────┼──────────┼──────────┤
│              assertions │        1 │        1 │
├─────────────────────────┴──────────┴──────────┤
│ total run duration: 1917ms                    │
├───────────────────────────────────────────────┤
│ total data received: 14B (approx)             │
├───────────────────────────────────────────────┤
│ average response time: 1411ms                 │
└───────────────────────────────────────────────┘

  #  failure        detail

 1\.  AssertionFai…  response code is 200
                    at assertion:1 in test-script
                    inside "Status Code Test" of "Example Collection with
                    Failing Tests"
```

The results of all tests and requests can be exported into a file. Use the JSON reporter and a file name to save the output into a file.

```
$ kafkaman-cli run mycollection.json --reporters cli,json --reporter-json-export outputfile.json
```

**Note:** kafkaman-cli allows you to use all [libraries and objects](/docs/writing-scripts/script-references/kafkaman-sandbox-api-reference/) that kafkaman supports to run tests and pre-request scripts.

## Using kafkaman-cli with CI/CD

By default, kafkaman-cli exits with a status code of 0 if everything runs as expected with no exceptions. You can configure your continuous integration tools to respond to kafkaman-cli's exit codes and correspondingly pass or fail a build. You can also utilize the `--bail` flag to make kafkaman-cli stop the run if it encounters a test case error with a status code of 1, which can then be picked up by your CI tool or build system.

## File uploads

kafkaman-cli also supports file uploads. For this to work correctly, upload the file in the relative location specified in the collection. For instance, review this collection:

```json
{
    "variables": [],
    "info": {
        "name": "file-upload",
        "_kafkaman_id": "9dbfcf22-fdf4-f328-e440-95dbd8e4cfbb",
        "description": "A set of `POST` requests to upload files as form data fields",
        "schema": "https://schema.getkafkaman.com/json/collection/v2.0.0/collection.json"
    },
    "item": [
        {
            "name": "Form data upload",
            "event": [
                {
                    "listen": "test",
                    "script": {
                        "type": "text/javascript",
                        "exec": [
                            "var response = JSON.parse(responseBody).files[\"sample-file.txt\"];",
                            "",
                            "tests[\"Status code is 200\"] = responseCode.code === 200;",
                            "tests[\"File was uploaded correctly\"] = /^data:application\\/octet-stream;base64/.test(response);",
                            ""
                        ]
                    }
                }
            ],
            "request": {
                "url": "https://kafkaman-echo.com/post",
                "method": "POST",
                "header": [],
                "body": {
                    "mode": "formdata",
                    "formdata": [
                        {
                            "key": "file",
                            "type": "file",
                            "enabled": true,
                            "src": "sample-file.txt"
                        }
                    ]
                },
                "description": "Uploads a file as a form data field to `https://kafkaman-echo.com/post` via a `POST` request."
            },
            "response": []
        }
    ]
}
```

The file ``sample-file.txt`` must be present in the current working directory as the collection. Run this collection as usual.

```bash
$ kafkaman-cli run file-upload.kafkaman_collection.json
```

## Library

kafkaman-cli has been built as a library from the ground up. It can be extended and used in various ways. You can use it as follows in your Node.js code:

```javascript
var kafkaman-cli = require('kafkaman-cli'); // require kafkaman-cli in your project

// call kafkaman-cli.run to pass `options` object and wait for callback
kafkaman-cli.run({
    collection: require('./sample-collection.json'),
    reporters: 'cli'
}, function (err) {
    if (err) { throw err; }
    console.log('collection run complete!');
});
```

## Custom reporters

Custom reporters come in handy when one would want to generate collection run reports that cater to very specific use cases.
For instance, logging out the response body when a request (or its tests) fail, and so on.

## Building custom reporters

A custom reporter is a Node module with a name of the form `kafkaman-cli-reporter-<name>`. To create a custom reporter:

1. Navigate to a directory of your choice, and create a blank npm package with `npm init`.

2. Add an `index.js` file, that exports a function of the following form:

```javascript
function (emitter, reporterOptions, collectionRunOptions) {
  // emitter is is an event emitter that triggers the following events: https://github.com/kafkamanlabs/kafkaman-cli#kafkaman-clirunevents
  // reporterOptions is an object of the reporter specific options. See usage examples below for more details.
  // collectionRunOptions is an object of all the collection run options:
  // https://github.com/kafkamanlabs/kafkaman-cli#kafkaman-clirunoptions-object--callback-function--run-eventemitter
};
```

1. Publish your reporter using `npm publish`, or use your reporter locally. See the usage instructions for more information.

Scoped reporter package names like `@myorg/kafkaman-cli-reporter-<name>` are also supported.

## Using custom reporters

In order to use the custom reporter, it will have to be installed first. For instance, to use the kafkaman-cli TeamCity reporter, install the reporter package:

```bash
npm install kafkaman-cli-reporter-teamcity
```

Note that the name of the package is of the form `kafkaman-cli-reporter-<name>`, where `<name>` is the actual name of the reporter. The installation should be global if kafkaman-cli is installed globally, local otherwise. Run `npm install ...` with the `-g` flag for a global installation.

To use local (non-published) reporters, run the command `npm install <path/to/local-reporter-directory>` instead.

Use the installed reporter, either via the CLI, or programmatically. Here, the `kafkaman-cli-reporter` prefix is not required while specifying the reporter name in the options.

Scoped reporter packages must be specified with the scope prefix. For instance, if your package name is `@myorg/kafkaman-cli-reporter-name`, you must specify the reporter with `@myorg/name`.

CLI:

```bash
kafkaman-cli run /path/to/collection.json -r myreporter --reporter-myreporter-<option-name> <option-value> # The option is optional
```

Programmatically:

```js
var kafkaman-cli = require('kafkaman-cli');

kafkaman-cli.run({
   collection: '/path/to/collection.json',
   reporters: 'myreporter',
   reporter: {
     myreporter: {
       'option-name': 'option-value' // this is optional
     }
   }
}, function (err, summary) {
  if (err) { throw err; }
  console.info('collection run complete!');
});
```

In both cases above, the reporter options are optional.

For the complete documentation, see the [kafkaman-cli README](https://github.com/kafkamanlabs/kafkaman-cli).

For more information about collection runs, see:

* [Using the Collection Runner](/docs/running-collections/intro-to-collection-runs/)
* [Working with data files](/docs/running-collections/working-with-data-files/)
* [Building workflows](/docs/running-collections/building-workflows/)
* [Integration with Jenkins](/docs/running-collections/using-kafkaman-cli-cli/integration-with-jenkins/)
* [Integration with Travis CI](/docs/running-collections/using-kafkaman-cli-cli/integration-with-travis/)
* [kafkaman-cli with Docker](/docs/running-collections/using-kafkaman-cli-cli/kafkaman-cli-with-docker/)
