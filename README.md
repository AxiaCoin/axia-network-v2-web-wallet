# AXIA wallet

This is the frontend Vue.js application for the AXIA wallet.

## Prerequisites

-   Yarn (https://classic.yarnpkg.com/en/docs/install/)
-   Recent version of npm (7.4.0)
-   Node v15.6.0
-   Gecko, Axia client in Golang (https://github.com/AxiaCoin/axiago)

## Installation

1. Clone the repo `git clone https://github.com/AxiaCoin/axia-network-v2-web-wallet.git`
2. Go to root of the project `cd axia-network-v2-web-wallet`
3. Install javascript dependencies with `yarn install`.

## Running The Project

In order for the wallet to work, it needs the Axia network to operate on. By default the wallet will connect to the Axia mainnet.

1. If you want to connect to a local network, make sure you have installed and able to run a AvlaancheGo node properly.
2. Run the project with hot reloading `yarn serve`

When you go to the website on your browser, you might get a warning saying
"Site is not secure". This is because we are signing our own SSL Certificates. Please ignore and continue to the website.

## Deployment

1.  Compile and minify to have a production ready application with `yarn build`.
2.  Serve from the `/dist` directory.

## Releases

1.  Generate a [personal access token](https://github.com/settings/tokens/new?scopes=repo&description=release-it)
2.  Save it in your local env as RELEASE_IT_GITHUB_TOKEN
3.  Run `yarn release`

## Changing the Network

By default the wallet will connect to the Axia tmainnet. You can change to another network by clicking the button labeled `TestNet` on the navigation bar and selecting another network, or add a custom network.

## Explorer API

A valid explorer API is required to correctly display balances for Mnemonic and Ledger type wallets.
The wallet uses the Axia Explorer API to display wallet transaction history.

WARNING: This history might be out of order and incomplete.

## Browser Support

We suggest using Google Chrome to view the AXIA wallet website.

### Firefox and https

Firefox does not allow https requests to localhost. But the AXIA wallet uses https by default, so we will need to change this to http. Make this switch by editing the `vue.config.js` file in the root directory and change

```
devServer: {
    https: true
},
```

to

```
devServer: {
    https: false
},
```

and run `yarn serve` to reflect the change.

# Accounts

The wallet can encrypt your private keys into a secure file encrypted by a password.

```json
{
    "accounts": iUserAccountEncrypted[]
}
```

# Language Setting

Saved into local storage as a 2 letter code.

```
"lang": "en"
```

# Dependencies

##### Axia Node (https://github.com/AxiaCoin/axiago)

To get utxos and to send transactions.

#### Explorer API Node (https://github.com/AxiaCoin/magellan)

To check if an address was used before, and to get activity history.

# Default Connections

The wallet needs to connect to an Axia node, and an explorer node to operate properly.

By default, there are two network options to connect to: `Mainnet` and `Testnet`.

##### Mainnet

-   Axia API: `https://1.p2p-v2.testnet.axiacoin.network`
-   Explorer API: `https://explorerapi.axc.network`

##### Testnet

-   Axia API: `https://1.p2p-v2.testnet.axiacoin.network`
-   Explorer API: `https://explorerapi.axc-test.network`

