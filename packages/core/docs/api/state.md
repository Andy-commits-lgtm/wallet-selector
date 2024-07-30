## API Reference (State)
### `.contracts`

**Returns**

- `MultiContractState`
  - `contractId` (`string`): Account ID of the Smart Contract.
  - `methodNames` (`Array<string>`): List of methods that can only be invoked on the Smart Contract. Empty list means no restriction.

**Description**

Returns the signed in contracts when signing-in with `signInMulti`.

**Example**

```ts
// MultiContractState = Array<ContractState>;
const { contracts } = selector.store.getState();
console.log(contracts); // [{ contractId: "test.testnet", methodNames: [] }, { contractId: "test1.testnet", methodNames: [] }]
```

### `.modules`

**Returns**

- `Array<ModuleState>`
  - `id` (`string`): Unique identifier for the wallet
  - `type` (`string`): Type of the wallet.
  - `metadata` (`string`): Meta information about the wallet.
  - `wallet` (`Function<Promise<Wallet>>`): Access functionality of the wallet.

**Description**

Returns the list of available modules.

**Example**

```ts
const { modules } = selector.store.getState();
console.log(modules); // [{ id: "my-near-wallet", ... }]
```

### `.accounts`

**Returns**

- `Array<AccountState>`
  - `accountId` (`string`): NEAR account identifier.
  - `publicKey` (`string?`): Account public key.
  - `active` (`boolean`): Is account set as active.

**Description**

Returns the list of signed in accounts.

**Example**

```ts
const { accounts } = selector.store.getState();
console.log(accounts); // [{ accountId: "test.testnet" }]
```

### `.selectedWalletId`

**Returns**

- `string | null`

**Description**

Returns the ID of the selected wallet.

**Example**

```ts
const { selectedWalletId } = selector.store.getState();
console.log(selectedWalletId); // "my-near-wallet"
```

### `.recentlySignedInWallets`

**Returns**

- `Array<string>`: List of wallet ID-s

**Description**

Returns ID-s of 5 recently signed in wallets.

**Example**

```ts
const { recentlySignedInWallets } = selector.store.getState();
console.log(recentlySignedInWallets); // ["my-near-wallet", "sender", ...]
```
