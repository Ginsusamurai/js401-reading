# Class 01 Reading

 Developer Consistency

## File Name Consistency
  
* File names are treated differently across different systems. Use a consistent format to ensure consistent behavior
  * lower case: case sensitivity some times is used, other times not
  * kabob-case: use-this-to-ensure-spaces-are-not-a-problem
  * ALL CAPS: THIS PUTS THE FILE AT THE TOP OF THE LIST, like with README.md
  
## Node.js

* This is an open source system with the V8 js runtime (supporting ES6/ES2015) and NodeAPIs (written in C, C++, JS)
* to handle asynchronus work, Node uses an event loop architecture that handles the processing for you

## package.json

* this file configures a Node.js package
  * `name` and `version` are only required fields
  * `npm init` and `npm init -y` automate the file creation and handling of dependencies, listing them under `dependencies` and `devDependencies`

## Semantic Versioning

* also known as `semver`
* `MAJOR.MINOR.PATCH`
  * `MAJOR` for when you make incompatible API changes
  * `MINOR` add backwards-compatible functionality
  * `PATCH` make backwards-compatible bug fixes

## CommonJS modules

* `CommonJS Modules` allow devs to organize code in to small files of defined functionality. This is key to scalability
* anything in `module.exports` can be accessible to another module through the `require` function
* `require` needs a path provided to work
* modules can not be co-dependent: A needs B, but B can't need A in turn

## Test Driven Development (TDD)

* methodology for writing code with short dev cycle to speed up dev time, validate code and understand goals. 3 steps of this:
  * RED - plan code and write tests for expected behavior that should fail
  * GREEN - write code to pass specs of tests, don't worry about optimization, test should pass
  * REFACTOR - refactor code for speed, memory, legibility
* install `jest` and `eslint` for dependencies, with a valid `.eslintrc.json` file and be able to run tests

## Continuous Integration (CI)

* regular merging of developed features in to shared repo as they are done
* works well with automated tests, code reviews, testing support, more.

## Continuous Delivery (CD)

* Deploying in short Cycles
* Code always ready to deploy
* Often paired with CI to enforce stability

## Github Actions

* Github Actions is a CI system
* actions handled via rules `.yml` format, in the `.github/workspaces` in the root directory of repo with details of project (language, build/test envs, and more)
* github will automatically run tests on push/PR, enforces tests passing to merge

## TDD in JS

* Devs spend more time MAINTAINING code, then writing code
* with that in mind, it makes sense to decrease maintenance rather than make it easy to write new code
* using TDD, you can decrease the subsequent cost of dev for future steps
* jest, selenium, multiple tools can be used for different testing uses
* use tools that make sense to implement - 'new for the sake of new' isn't helpful, the tool has to 'pay for itself'

## About NPM

* `npm` let's you publish packages/modules for others to use
* can also be used internally to re-use code across projects
* use npm client locally to upload/download on the NPM website

## [NPM docs](https://docs.npmjs.com/getting-started/)

* setting up an account ont he npm site allows for uploading
* free accounts have public packages, paid accounts for private packages

## [Jest](https://jestjs.io/docs/en/getting-started)

* test runner for JS
* can use `Babel` (JS compiler) to convert your JS code to browser-compatible JS (some tools don't work with certain browsers)
* typeScript and other features are also compatible with jest
* to use, specific test scripts need to be built
  
  ``` javascript
  test('description of test', () => {
    expect(2+2).toBe(4);
  });
  ```
  
  * this format creates a test, which only executes via jest, that has an input, a comparison operator, and a target value
  * tests can run specific functions, check state, check not-state, employ `truthy-ness`, type and more