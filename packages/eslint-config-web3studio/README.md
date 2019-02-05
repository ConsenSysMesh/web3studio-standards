# Web3Studio ESlint Config

Eslint config for web3studio projects.

## Installation

```bash
$ yarn add --dev eslint-config-web3studio eslint prettier pretty-quick husky
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

## License

[Apache 2.0](LICENSE)
