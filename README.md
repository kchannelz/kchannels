# Kchannels
Pronounced kay-channels.  Formerly known as Infura Payment Channels.

Kchannels is a non-custodial payment channel product for [Ethereum](https://ethereum.org/) that utilizes proven solutions from the legacy financial industry and combines them with Layer 2 tech based on our learnings and experience from [Infura](https://infura.io/), a popular Ethereum infrastructure provider.

From the beginning, Kchannels was designed for good user and developer experience.  It delivers the three canonical benefits of payment channels (real-time speed, low transaction costs, and privacy) along with a host of other benefits.

At the core of Kchannels are *multi-channels*, a new type of payment channel construction that helps to deliver a remarkably frictionless payment channel experience.


## Status
Kchannels has undergone an extended design process, with input and feedback from members of [ConsenSys](https://consensys.net/).  We recently completed the MVP code and are in the process of testing and integration.  We are planning to launch on a testnet toward the end of October 2019.


## Features
### Canonical payment channel features
* Fast (real-time) transactions
* Low cost per transaction relative to Mainnet
* Privacy

### High-level features
* Always non-custodial
* No token(s) to drive functionality
* No capital required to maintain channel functionality
* No payment channel network
* Robust dispute resolution
* Flexible fee system
* Supports partial or full trustlessness
* Minimal infrastructure requirements for end users
* Designed for good user and developer experience
* Horizontal scaling to support very high throughput

### Channel (*multi-channel*) features
* Support for ether and ERC-20 tokens
* Support for multiple assets in a single channel
* A client has the ability to add assets to and withdraw assets from an open channel
* A client is not required to be online to receive assets
* A client can safely walk away from an open channel without withdrawing; there is no risk of losing funds while he’s not paying attention
* A client can immediately transact with any other client that has an open channel in the system
* Each channel can be in one of two modes:  Light Mode or Watchtower Mode


## Architecture
Kchannels is built around the notion of a *deployment*, which is analogous to a hub in other solutions.  A deployment consists of two main components:  a set of smart contracts on the Ethereum blockchain and a set of services running in a hosted environment.  This allows for transparent maintenance and upgrades on the backend as well as for reducing the infrastructure burden on end users while maintaining our trustlessness guarantees.  The use of only a small set of smart contracts helps reduce contract tracking and gas costs (i.e. there are no per-channel contracts).

All assets are stored in a single smart contract, and the deployment tracks title (ownership) of those assets off-chain.

A deployment facilitates transactions between clients--nothing more and nothing less.  An in-flight transaction is validated and signed every step of the way (by the sender, recipient, and deployment), so a deployment can **never** meddle with the contents of a transaction.  Because of this extensive validation, any disputes that arise are between a client and the deployment, not between a client and his counterparty.  This greatly simplifies dispute resolution.

Clients **always** have the ability to bypass the deployment and withdraw their funds directly from the smart contract by submitting the usual proofs.  If a proof is old or otherwise invalid, it will be challenged by the deployment as part of a formal and provably fair dispute resolution process.

Internally, a deployment supports horizontal scaling, making it possible for Kchannels to achieve very high throughput.


## Roadmap
* We are open to interoperating with other payment channel solutions.
* In the future, we believe we will be able to support not just payment channels but also *state* channels.
* There are a lot of other cool features on our roadmap, so stay tuned.


## Links
Most of these are not set up yet, but will be soon.
* [Twitter](https://twitter.com/kchannelsio)
* [Website](http://kchannels.io/)
* [Blog](https://medium.com/kchannels)


## What's up with the "kchannelz" part in the GitHub URL?
Well, https://github.com/kchannels was taken :(


## Colophon
![Built on Ethereum](https://raw.githubusercontent.com/ethhub-io/ethhub/master/docs/assets/files/builtoneth_branding/PNG/Tall%20light%20color.png "Built on Ethereum")
