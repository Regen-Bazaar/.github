<p align="center">
  <img src="images/logo-512.png" width="96" alt="Regen Bazaar logo">
</p>

<h1 align="center">Regen Bazaar</h1>

<p align="center">
  <b>Fund verified real-world impact on-chain, paid in USDG, with provenance anyone can check.</b>
</p>

<p align="center">
  <a href="https://app.regenbazaar.com"><b>Try the beta</b></a> ·
  <a href="https://github.com/Regen-Bazaar/regenbazaar-beta">Source</a> ·
  <a href="https://github.com/Regen-Bazaar/regenbazaar-beta/blob/main/docs/ARCHITECTURE.md">How it works</a> ·
  <a href="https://github.com/Regen-Bazaar/regenbazaar-beta/blob/main/docs/ROADMAP.md">Roadmap</a> ·
  <a href="https://www.regenbazaar.com">Website</a> ·
  <a href="https://x.com/RegenBazaar">X</a> ·
  <a href="https://t.me/regen_bazaar">Telegram</a>
</p>

<p align="center">
  <img src="images/2-marketplace.png" width="820" alt="Regen Bazaar marketplace with tRWI cards">
</p>

> **Status:** public beta on testnets (Arbitrum Sepolia and Robinhood Chain testnet). No real funds, no production users yet.

## What it is

Small NGOs and community groups do measurable good: reforestation, cleanups, animal rescue, education. They rarely have a way to turn that work into something a funder can buy, hold and verify.

Regen Bazaar turns an NGO's impact report into **tRWI** (tokenized real-world impact): fractional ERC-1155 editions backed by an on-chain attestation. Funders pay in **USDG**, and the NGO is paid in the same transaction.

## How it works

1. **Report.** An NGO describes its impact in plain language. An LLM extracts the actions and numbers; it never scores.
2. **Score.** A deterministic, versioned formula computes the Impact Value. Weights are v0.1, published at [`/methodology`](https://app.regenbazaar.com/methodology), platform-assessed, not third-party certified.
3. **Verify.** A human validator approves. Metadata is pinned to IPFS and the claim is attested on-chain with EAS.
4. **Fund.** A funder buys editions in USDG. The token is lazily minted at purchase from a platform-signed voucher; 97.5% goes straight to the NGO wallet, 2.5% is the platform fee.
5. **Hold or retire.** Editions show up on the funder's **My impact** page and can be retired to claim the impact permanently.

| Home | On-chain proof | Submit impact |
|---|---|---|
| ![Home](images/1-home.png) | ![Project page with on-chain proof](images/3-proof.png) | ![Impact submission form](images/4-tokenize.png) |

## Networks and contracts

One site, two networks: the visitor picks the network in the header. Core contracts share the same addresses on both chains and are source-verified.

| Network | Payment | Explorer |
|---|---|---|
| Arbitrum Sepolia (421614) | tUSDG, a labelled testnet stand-in, while the Paxos USDG faucet is not dispensing there; Paxos USDG is already allowlisted | [RegenPrimarySale on Blockscout](https://arbitrum-sepolia.blockscout.com/address/0x79E4bEAF41F415cE3DF55DaDe3F86423e5399030) |
| Robinhood Chain testnet (46630) | Paxos USDG (testnet) | [RegenPrimarySale on Blockscout](https://explorer.testnet.chain.robinhood.com/address/0x79E4bEAF41F415cE3DF55DaDe3F86423e5399030) |

Example purchase, paid in Paxos USDG on Robinhood Chain testnet, split to the NGO in one transaction: [`0xea4a18d2…`](https://explorer.testnet.chain.robinhood.com/tx/0xea4a18d20c2fc3c4ed2a46ef7681129a99b905118745ff2de9ad95609ca2ba77)

The same contracts are also deployed and source-verified on Celo Sepolia (not offered in the site's network switcher).

All addresses and proof transactions: [`packages/contracts/deployments`](https://github.com/Regen-Bazaar/regenbazaar-beta/tree/main/packages/contracts/deployments).

## Try it

- **Without a wallet:** browse the [marketplace](https://app.regenbazaar.com) and open any project to see its attestation and transactions.
- **For AI agents and developers:** a public machine-readable catalogue at [`/api/impact`](https://app.regenbazaar.com/api/impact).
- **With a wallet:** switch to either testnet, get test tokens (the in-app guide lists working faucets), press *Fund this impact*, then open *My impact*.

## Where this comes from

Before Regen Bazaar, the same model ran as two single-organisation pilots: [Clean Phangan](https://cleanphangan.regenbazaar.com) (community beach cleanups, Koh Phangan) and [EcoThailand Foundation](https://ecothailand.regenbazaar.com) (mangrove restoration). Regen Bazaar generalises them into a multi-organisation marketplace.

## Roadmap

- **Now:** public testing with the community.
- **Next, trust:** calibrate Impact Value weights with domain experts; geotagged evidence; duplicate and cross-registry checks; revocation flow.
- **Next, NGOs:** organisation profiles and team roles; email or Telegram sign-in with an embedded wallet.
- **Next, funders:** mobile wallets, gasless checkout, card on-ramp, shareable impact certificates.
- **Before mainnet:** external security audit, multisig with timelock, legal review.

Full list: [ROADMAP.md](https://github.com/Regen-Bazaar/regenbazaar-beta/blob/main/docs/ROADMAP.md)

## Repositories

- [**regenbazaar-beta**](https://github.com/Regen-Bazaar/regenbazaar-beta): the app, contracts, Impact Value engine and indexer (active)
- [**landing**](https://github.com/Regen-Bazaar/landing): [www.regenbazaar.com](https://www.regenbazaar.com)
- Earlier prototypes (multi-chain contracts, first dApp, monorepo) are archived and kept read-only for history.
