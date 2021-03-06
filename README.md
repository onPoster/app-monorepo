```
██████╗  ██████╗ ███████╗████████╗███████╗██████╗
██╔══██╗██╔═══██╗██╔════╝╚══██╔══╝██╔════╝██╔══██╗
██████╔╝██║   ██║███████╗   ██║   █████╗  ██████╔╝
██╔═══╝ ██║   ██║╚════██║   ██║   ██╔══╝  ██╔══██╗
██║     ╚██████╔╝███████║   ██║   ███████╗██║  ██║
╚═╝      ╚═════╝ ╚══════╝   ╚═╝   ╚══════╝╚═╝  ╚═╝
    ___              
   /   |  ____  ____ 
  / /| | / __ \/ __ \
 / ___ |/ /_/ / /_/ /
/_/  |_/ .___/ .___/ 
      /_/   /_/      
```

An app for showcasing [ERC-3722 – Poster](https://ethereum-magicians.org/t/erc-3722-poster-a-ridiculously-simple-general-purpose-social-media-smart-contract/6751). This is a monorepo fetching all components as [`git submodules`](https://git-scm.com/book/en/v2/Git-Tools-Submodules), which can be found in our [organization](https://github.com/onPoster).

1. [`Poster`](https://github.com/onPoster/app) - An EVM-compatible append-only general purpose smart contract.
1. [`Subgraph`](https://github.com/onPoster/subgraph) - An indexer and content parser for Poster powered by TheGraph.
1. [`App`](https://github.com/onPoster/app) - A sample UI to showcase ERC-3722 usage as a protocol for social apps.

# Setup (cloud)

## Launch with Gitpod

The easiest way to setup `Poster App` is by running it via [Gitpod.io](https://gitpod.io/#https://github.com/onPoster/app-monorepo). It will automatically spin a cloud instance with all the required commands and dependencies ready to go.

[![Open in Gitpod](https://gitpod.io/button/open-in-gitpod.svg)](https://gitpod.io/#https://github.com/onPoster/app-monorepo)

Please wait until all services have started. Afterwards, you will be able to connect to the application via MetaMask in the next step.

## Connect to Gitpod's `hardhat` node with MetaMask

1. Make sure you have downloaded [MetaMask](https://metamask.io) browser extension.
2. Create a new wallet[^1] and import the following private key:

```
ac0974bec39a17e36ba4a6b4d238ff944bacb478cbed5efcae784d7bf4f2ff80
```

3. Add the `hardhat` in your MetaMask “Networks” section:

```
Network Name: Gitpod Hardhat
New RPC URL: <at the bottom of the website, should be something like https://8545-onposter-...3cs.ws-eu27.gitpod.io
Chain Id: 31337
```

Your balance should be around 9999.95 ETH or so. If you restart the project, you might need to reset your MetaMask account so the transactions come from the first block again, which you can do by going to "Advanced > Reset Account”. **IMPORTANT: Only do this on a wallet that has the Hardhat test mnemonic imported, as this will affect ALL your accounts and not the only one the imported one.**

# Setup (locally)

## Clone repository with all submodules

`git clone git@github.com:onPoster/app-monorepo.git --recurse-submodules`

## Install dependencies and run all services

1. `yarn`
1. `yarn run:local:node`
1. (In new terminal) `yarn deploy:local:contracts`
1. `yarn run:local:subgraph`
1. (In new terminal) `yarn config:local:subgraph`
1. `yarn build:local:subgraph`
1. `yarn deploy:local:subgraph`
1. `yarn run:local:app`

## Connect to `localhost`

1. Follow the first `2` steps in `Connect to Gitpod’s hardhat node with MetaMask` section
1. Add the `hardhat` in your MetaMask “Networks” section instead of Gitpod's Hardhat:

```
Network Name: Hardhat
New RPC URL: http://localhost:8545
Chain Id: 31337
```

# Using the application

With the application up and running, go to `localhost:3000` or browse the automatic preview pane opened by Gitpod, and connect your wallet with the “Connect wallet” option. This will allow you to submit transactions to your local hardhat node.

Write anything in the text field, and submit the transaction. You will be able to see how the posts are loaded and shortly after your post will show.

---

[^1]: You can always simply import Hardhat's demo mnemonic `test test test test test test test test test test test junk`. Make sure to not send any real digital assets to any of these accounts, as all their private keys are publicly known.
