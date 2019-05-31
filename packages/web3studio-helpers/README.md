<h1 align="center">
  Web3studio Helpers
  <br/>
</h1>

<h4 align="center">
 Common Setup and scripts for w3s projects
</h4>

<p align="center">
  <a href="#truffle-setup">Truffle Setup</a>
  <a href="#license">License</a>
</p>

This project contains common code used to bootstrap tests and common scripts.

<br/>

## Truffle Setup

Create a `truffle-config.js`, and a global test setup file.

```js
// truffle-config.js
module.exports = require('web3studio-helpers/truffle-config')(__dirname, {
  // defaults
  mainnetGasPrice: '0',
  solcVersion: '0.5.4',
  ignoreFilesGlobs: ['**/node_modules/**', '**/Migrations.sol']
});
```

```js
// test/global.js
require('web3studio-helpers/truffleTestGlobals');
```

## Environment Variables

You'll need to set some environment variables to use the config on a testnet or mainnet. You can do so either via your shell or with a `.env` file

```bash
# .env
INFURA_API_KEY="<YOUR_INFURA_KEY>"
SEED_PHRASE="<YOUR_WALLET_SEED_PHRASE>"
```

## License

[Apache 2.0](LICENSE)
