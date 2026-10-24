[README.md](https://github.com/user-attachments/files/33908657/README.md)
# Steem Wallet

**Steem Wallet** is an independent, browser-based wallet for the Steem blockchain. It provides a simple interface for viewing account information and managing STEEM, SBD and STEEM POWER (SP).

The wallet opens an account in **read-only mode using only a Steem username**. No private key is required to check balances, delegations, rewards or transaction history. When you decide to perform a transaction, the wallet asks for your **Active Private Key (WIF)** specifically for that operation.

The project was initiated by @MaxArt and developed with AI assistance. It is not an official Steemit product and is not affiliated with Steemit or other Steem ecosystem services.

## Features

- **Read-only access:** open any Steem account by username without entering a private key.
- **Balances:** view STEEM, SBD and STEEM POWER, including available and delegated SP.
- **Transfers:** send STEEM or SBD to another Steem account, with an optional memo.
- **Power Up:** convert liquid STEEM into STEEM POWER.
- **Delegation management:** delegate SP, review incoming and outgoing delegations, cancel outgoing delegations and view SP pending return.
- **Rewards:** view and claim available rewards.
- **Transaction history:** review account operations from the last 14 days.
- **English-only interface.**
- **Single-file distribution:** the complete application, including its JavaScript libraries and styles, is contained in `index.html`.

## Getting started

### Run locally

1. Download `index.html`.
2. Open it in a modern browser, such as Chrome or Edge.
3. Enter your Steem account name and select **Open wallet**.
4. View account data without providing a private key.
5. To perform a transaction, enter your **Active Private Key** in the operation's signing dialog, then confirm.

**An internet connection is required.** The wallet communicates with the Steem blockchain via `https://api.steemit.com`. Some browsers or configurations restrict network requests from pages opened using `file://`. If local requests are blocked, use an HTTPS-hosted copy, such as GitHub Pages.

### Publish with GitHub Pages

1. Create a GitHub repository and upload `index.html` to its root.
2. Open **Settings → Pages** in the repository.
3. Under **Build and deployment**, select **Deploy from a branch**.
4. Select the `main` branch and `/ (root)` folder, then save.
5. Once deployed, open the GitHub Pages URL shown in the repository settings.

No PHP backend, build process, package manager or CDN is required for this version.

## Private key handling

- A private key is **not required for read-only account access**.
- The **Active Private Key (WIF)** is requested only when a specific operation needs to be signed.
- Signing is performed in the browser using the bundled dsteem library.
- The key is not intentionally saved to local storage, cookies or a developer-controlled server. The signing dialog clears its input after use.
- The Steem username may be remembered in browser local storage for convenience.
- **Never enter your Owner Key** for routine wallet transactions.

This design reduces unnecessary exposure of the Active Key, but it does **not** guarantee protection against malware, malicious browser extensions, a compromised device or a modified copy of the wallet. Review the source and use a trusted environment before signing transactions.

## Technology

- HTML, CSS and JavaScript
- Bundled `steem-js` and `dsteem` libraries
- Steem JSON-RPC API: `https://api.steemit.com`
- No required server-side wallet component

## Important notice

This software is provided free of charge **as is**, without warranties. Blockchain transactions are irreversible. Verify account names, amounts, delegation details and memos before signing.

The developer does not guarantee uninterrupted availability of the Steem API, transaction processing, security or preservation of digital assets. **Use at your own risk.**
