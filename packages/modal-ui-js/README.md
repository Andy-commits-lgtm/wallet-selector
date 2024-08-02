# @near-wallet-selector/modal-ui-js

This is the Modal UI package for NEAR Wallet Selector.

## Installation and Usage

The easiest way to use this package is to install it from the NPM registry:

```bash
# Using Yarn
yarn add @near-wallet-selector/modal-ui-js

# Using NPM.
npm install @near-wallet-selector/modal-ui-js
```

Then use it in your dApp:

```ts
import { setupWalletSelector } from "@near-wallet-selector/core";
import { setupModal } from "@near-wallet-selector/modal-ui-js";
import { setupMyNearWallet } from "@near-wallet-selector/my-near-wallet";

const selector = await setupWalletSelector({
  network: "testnet",
  modules: [setupMyNearWallet()],
});

const modal = setupModal(selector, {
  contracts: [{ receiverId: "test.testnet", methodNames: [] }]
});

modal.show();
```

## Options

- `theme` (`Theme?`): Specify light/dark theme for UI. Defaults to the browser configuration when omitted or set to 'auto'. This can be either `light`, `dark` or `auto`.
- `description` (`string?`): Define a custom description in the UI.
- `contracts` (`Array<{allowance?: BN, receiverId: string, methodNames: Array<string>}>?`): List of the Smart Contracts and the limited access to particular methods on the Smart Contract for signing in with multiple contracts. When the list of contracts is provided the `signInMulti` method of the wallets is used by default to sign-in.


## Styles & Customizing CSS

Import modal css styles:

### Angular

```css
/* Add import in the main css file */
@import "~@near-wallet-selector/modal-ui-js/styles.css";
```

### React & Vue

```ts
// Add import in the main component
import "@near-wallet-selector/modal-ui-js/styles.css";
```

These are the available css variables:

```css
--backdrop-bg
--heading-color
--text-color
--sidebar-border-color
--selected-wallet-bg
--selected-wallet-bg-hover
--wallet-option-border-color
--wallet-option-bg-hover
--content-bg
--change-path-bg
--home-button-bg
--confirm-button-bg
--confirm-button-bg-hover
--error
--close-button-bg-color
--close-button-fill-icon-colo
--spinner-color
--bottom-section
--mobile-text
--connected-green
```

Customizing css is done simply by updating the value of a variable in the root of your css file.

```css
:root {
  --backdrop-bg: #26262630;
}
```

## API Reference

You can find the entire API reference for Modal UI [here](./docs/api/modal.md).

## License

This repository is distributed under the terms of both the MIT license and the Apache License (Version 2.0).
