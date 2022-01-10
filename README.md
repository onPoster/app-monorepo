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

# Usage

## Clone repository with all submodules

`git clone git@github.com:onPoster/app-monorepo.git --recurse-submodules`

## Setup project for development

1. `yarn`
1. `yarn run:local:node`
1. (In new terminal) `yarn deploy:local:contracts`
1. `yarn run:local:subgraph`
1. (In new terminal) `yarn config:local:subgraph`
1. `yarn build:local:subgraph`
1. `yarn deploy:local:subgraph`
1. `yarn run:local:app`