lambda-function-search
======================

Search your Lambda functions

[![oclif](https://img.shields.io/badge/cli-oclif-brightgreen.svg)](https://oclif.io)
[![Version](https://img.shields.io/npm/v/lambda-function-search.svg)](https://npmjs.org/package/lambda-function-search)
[![Downloads/week](https://img.shields.io/npm/dw/lambda-function-search.svg)](https://npmjs.org/package/lambda-function-search)
[![License](https://img.shields.io/npm/l/lambda-function-search.svg)](https://github.com/hideokamoto/lambda-function-search/blob/master/package.json)

<!-- toc -->

## Requirements

- Node.js >= 18.0.0

## What's New in v0.6.0

- ✨ **Modernized Dependencies**: Migrated to AWS SDK v3 and oclif v4
- 🔒 **Security**: Fixed all 12 security vulnerabilities
- 🚀 **Updated Runtime Support**: Added support for latest Lambda runtimes (Node.js 18/20/22, Python 3.11/3.12/3.13, etc.)
- 🌍 **Expanded Regions**: Updated AWS region list to include all current regions
- 🛠️ **Developer Experience**: Migrated from TSLint to ESLint, updated TypeScript to v5

# Install

```
$ npm i -g lambda-function-search

```

# Usage

```
$ lfs --help
Search Lambda functions

USAGE
  $ lambda-function-search

OPTIONS
  -A, --showAll          Show all function data

  -R, --runtime=runtime  Lambda runtime
                         Example: nodejs18.x, nodejs20.x, nodejs22.x,
                         python3.11, python3.12, python3.13,
                         java11, java17, java21,
                         dotnet6, dotnet8,
                         ruby3.2, ruby3.3,
                         provided.al2, provided.al2023

  -h, --help             show CLI help

  -p, --profile=profile  AWS CLI profile

  -r, --region=region    region

  -s, --search=search    search by name
```

<!-- usage -->
# Commands

## List all Function
```bash
$ lfs --region us-east-1
Matched Functions: 5 / 5
====
ContactFormLambda
serverlessContactForm
HelloAlexa
Example
ServerlessTest
```

## List All Functions (ALL Regions)

```bash
$ lfs --region all
=== Matched Functions: 5 / 5 ===
Region : ap-northeast-2
ContactFormLambda
serverlessContactForm
HelloAlexa
Example
ServerlessTest
=== Matched Functions: 2 / 5 ===
Region : ap-northeast-1
ContactFormLambda
serverlessContactForm
...
```

## Search by Runtime

```bash
$ lfs --region us-east-1 --runtime nodejs20.x
Search condition: Runtime === nodejs20.x
Matched Functions: 5 / 43
====
ContactFormLambda
serverlessContactForm
HelloAlexa
Example
ServerlessTest
```

## Search by FunctionName

```bash
$ lfs --region us-east-1 --search Form
Search condition: FunctionName contains Form
Matched Functions: 2 / 43
====
ContactFormLambda
serverlessContactForm
```
