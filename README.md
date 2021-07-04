# moralis-web3-providers-ws

[![NPM Package][npm-image]][npm-url] [![Dependency Status][deps-image]][deps-url] [![Dev Dependency Status][deps-dev-image]][deps-dev-url]

This is a fork of web3-providers-ws that uses https://github.com/MoralisWeb3/WebSocket-Node

This is a websocket provider sub-package for [web3.js][repo].

Please read the [documentation][docs] for more.

## Installation

### Node.js

```bash
npm install moralis-web3-providers-ws
```

## Usage

```js
const MoralisWeb3ProvidersWs = require('moralis-web3-providers-ws');

const options = {
    // Enable keepalive 
    clientConfig: {
        keepalive: true,
        keepaliveInterval: 60000,
        keepaliveForce: true
    },
    // Enable auto reconnection
    reconnect: {
        auto: true,
        delay: 5000, // ms
        maxAttempts: 5,
        onTimeout: false
    }
};

const wsProvider = new MoralisWeb3ProvidersWs('ws://localhost:8546', options);
```

## Usage with Web3

```js
const Web3 = require('web3');
const web3 = new Web3(wsProvider);
```

## Usage with Ethers.js

```js
const ethers = require('ethers');
const provider = new ethers.providers.Web3Provider(wsProvider);
```

Additional client config options can be found [here](https://github.com/theturtle32/WebSocket-Node/blob/v1.0.31/docs/WebSocketClient.md#client-config-options).

## Types

All the TypeScript typings are placed in the `types` folder.

[docs]: http://web3js.readthedocs.io/en/1.0/
[repo]: https://github.com/ethereum/web3.js
[npm-image]: https://img.shields.io/npm/v/web3-providers-ws.svg
[npm-url]: https://npmjs.org/package/web3-providers-ws
[deps-image]: https://david-dm.org/ethereum/web3.js/1.x/status.svg?path=packages/web3-providers-ws
[deps-url]: https://david-dm.org/ethereum/web3.js/1.x?path=packages/web3-providers-ws
[deps-dev-image]: https://david-dm.org/ethereum/web3.js/1.x/dev-status.svg?path=packages/web3-providers-ws
[deps-dev-url]: https://david-dm.org/ethereum/web3.js/1.x?type=dev&path=packages/web3-providers-ws
