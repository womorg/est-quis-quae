[![npm version](https://badge.fury.io/js/@womorg/est-quis-quae.svg)](https://www.npmjs.com/package/@womorg/est-quis-quae)
[![npm downloads](https://img.shields.io/npm/dt/@womorg/est-quis-quae.svg?logo=npm)](https://www.npmjs.com/package/@womorg/est-quis-quae)
[![Build Status](https://github.com/womorg/est-quis-quae/workflows/build/badge.svg)](https://github.com/womorg/est-quis-quae/actions)
[![Coverage Status](https://coveralls.io/repos/github/activescott/@womorg/est-quis-quae/badge.svg)](https://coveralls.io/github/activescott/@womorg/est-quis-quae)
[![License](https://img.shields.io/github/license/activescott/@womorg/est-quis-quae.svg)](https://github.com/womorg/est-quis-quae/blob/main/LICENSE)
[![GitHub stars](https://img.shields.io/github/stars/activescott/@womorg/est-quis-quae.svg?style=social)](https://github.com/womorg/est-quis-quae)

# @womorg/est-quis-quae

Locally invoke [Serverless](https://github.com/serverless/serverless) functions via their HTTP event as specified in Serverless.yml.

It makes it easy to test not only your handler logic, but also ensures that you have your http events setup properly in serverless.yml without deploying.

<!-- TOC -->

- [Usage / Quick Start](#usage--quick-start)
- [Prerequisites / Usage Requirements](#prerequisites--usage-requirements)
- [Install](#install)
- [Features](#features)
- [Contributing 🤝](#contributing-🤝)
- [Show your support](#show-your-support)
- [Release Process (Deploying to NPM)](#release-process-deploying-to-npm)
- [License 📝](#license-📝)

<!-- /TOC -->

## Usage / Quick Start

Use it in tests of Serverless functions to test your HTTP endpoints along with the handler code. For example, you can write the following to test a Serverless function:

    it('should invoke simple path', function () {
      let response = invoker.invoke('GET api/hello')
      return expect(response).to.eventually.have.property('statusCode', 200)
    })

The test above is a test of a Serverless function defined in a `Serverless.yml` as follows:

    functions:
      hello:
        handler: handler.hello
        events:
          - http:
              path: api/hello
              method: get

Some of the more common use cases are demonstrated in the basic tests at [the basic test cases](examples/basic/basic.spec.js).
An exhaustive list of what is supported in Some of the more common use cases are demonstrated in the basic tests at [the comprehensive test cases](examples/comprehensive/comprehensive.spec.js).

## Prerequisites / Usage Requirements

Requires Node.js latest, LTS, and v10 ([tested](https://travis-ci.org/activescott/@womorg/est-quis-quae)).

If you need Node.js v6.x - v9.x support you can use [@womorg/est-quis-quae@0.8.6](https://www.npmjs.com/package/@womorg/est-quis-quae/v/0.8.6).

Requires Serverless Framework v1.x.
If you are new to the Serverless Framework, check out the [Serverless Framework Getting Started Guide](https://serverless.com/framework/docs/getting-started/).

## Install

npm (`npm install @womorg/est-quis-quae --save-dev`) or yarn (`yarn add @womorg/est-quis-quae --dev`)

## Features

- Simple to reference your handler
- Tests the serverless route is configured in serverless.yml as well as your handler code
- Test Framework agnostic (mocha, jest, etc.)

## Contributing 🤝

This is a community project. We invite your participation through issues and pull requests! You can peruse the [contributing guidelines](.github/CONTRIBUTING.md).

## Show your support

Give a ⭐️ if this project helped you!

## Release Process (Deploying to NPM)

We use [semantic-release](https://github.com/semantic-release/semantic-release) to consistently release [semver](https://semver.org/)-compatible versions. This project deploys to multiple [npm distribution tags](https://docs.npmjs.com/cli/dist-tag). Each of the below branches correspond to the following npm distribution tags:

| branch | npm distribution tag |
| ------ | -------------------- |
| main   | latest               |
| beta   | beta                 |

To trigger a release use a Conventional Commit following [Angular Commit Message Conventions](https://github.com/angular/angular.js/blob/master/DEVELOPERS.md#-git-commit-guidelines) on one of the above branches.

## License 📝

Copyright © 2017 [Scott Willeke](https://github.com/activescott).

This project is [MIT](https://github.com/womorg/est-quis-quae/blob/main/LICENSE) licensed.
