swagger-examples-validator
==========================

Validates embedded examples in Swagger-specs (only JSON supported, yet)

[![npm version](https://badge.fury.io/js/swagger-examples-validator.svg)](https://badge.fury.io/js/swagger-examples-validator)
[![Standard Version](https://img.shields.io/badge/release-standard%20version-brightgreen.svg)](https://github.com/conventional-changelog/standard-version)
[![Build Status](https://travis-ci.org/codekie/swagger-examples-validator.svg?branch=master)](https://travis-ci.org/codekie/swagger-examples-validator)
[![Coverage Status](https://coveralls.io/repos/github/codekie/swagger-examples-validator/badge.svg?branch=master)](https://coveralls.io/github/codekie/swagger-examples-validator?branch=master)

Install
-------

Install using [npm](https://docs.npmjs.com/getting-started/what-is-npm):

    npm install -g swagger-examples-validator

Usage
-----

```
swagger-examples-validator [options] <filePath>

Validate embedded examples in Swagger-JSONs

Options:

  -h, --help     output usage information
  -V, --version  output the version number
````

The validator will search the Swagger-JSON for response-examples and
validate them against its schema.

Errors will be written to `stderr`.

Sample output of validation errors:

```json
[
    {
        "keyword": "type",
        "dataPath": ".versions[0].id",
        "schemaPath": "#/properties/versions/items/properties/id/type",
        "params": {
            "type": "string"
        },
        "message": "should be string",
        "examplePath": "/~1/get/responses/200/examples/application~1json"
    }
]
```

Test
----

To run the tests, execute

    npm test

or to check the coverage

    npm run coverage

Future features
---------------

- YAML support