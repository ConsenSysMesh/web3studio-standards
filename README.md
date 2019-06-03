# Web3Studio Standards

A collection of boilerplate config to be used by Web3Studio projects.

## Installation

```bash
$ yarn add --dev eslint-config-web3studio eslint prettier pretty-quick husky

# For projects with Smart Contracts
$ yarn add --dev solium-config-web3studio solium
```

In your `.eslintrc.js` file:

```js
module.exports = {
  extends: [
    'web3studio',
    'web3studio/truffle' // For projects using truffle
  ]
};
```

In your `.prettierrc.js` file:

```js
module.exports = require('eslint-config-web3studio/prettier');
```

In your `.soliumrc.json` file:

```json
{
  "extends": "web3studio",
  "plugins": ["security"]
}
```

In your `package.json` file:

```json
{
  "husky": {
    "hooks": {
      "pre-commit": "pretty-quick --staged"
    }
  },
  "scripts": {
    "lint": "yarn lint:js && yarn lint:sol",
    "lint:js": "eslint .",
    "lint:sol": "solium -d .",
    "prettier": "prettier \"**/*.{js,json,css,md}\" --write"
  }
}
```

## Releasing a New Version

**NB:** For maintainers only.

`web3studio-standards` uses [Semver](https://semver.org/) for versioning.
Based on the changes since the last release, determine which type of
release this is, `major`, `minor`, or `patch`.

Use lerna to update all of the packages to the new version, and create a pull
request. Travis will handle publishing to npm.

For example, to release a new major version...

```bash
$ git checkout -b release/v1.0.0
$ yarn lerna:version major
$ git push origin release/v1.0.0 --follow-tags

# Open a pull request from `release/v1.0.0` => `master`
```

## License

[Apache 2.0](LICENSE)
