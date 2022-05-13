# NEP141_Factory

## About NEP141_Factory
NEP141_Factory allows you to mint standard NFT(Non-Fungible-Token) of [NEAR-Protocol](https://github.com/near/NEPs/blob/ea409f07f8/specs/Standards/NonFungibleToken/Core.md).

## Getting Started
Clone this repository

```jsx
git clone https://github.com/kidrauhl14/NEP141_Factory
cd NEP141_Factory
```

Compile Contract code

```jsx
cargo build --target wasm32-unknown-unknown --release
```

Login
```jsx
near login
```

Deploy Contract

```jsx
near deploy --wasmFile NEP141_Factory.wasm --accountId $ACCOUNTID
```

Init Contract

```jsx
near call $ACCOUNTID new '{"owner_id": "$ACCOUNTID", "total_supply": "1000000000000000", "metadata": { "spec": "ft-1.0.0", "name": "$TOKEN_NAME", "symbol": "GGB", "decimals": 8 }}' --accountId $ACCOUNTID
```

Mint NFTs
```jsx
near call YOUR_ACCOUNT nft_mint '{"token_id":"TOKEN_ID", "token_owner_id":"OWNER_ACCOUNT", "token_metadata":{"title":"TOKEN_TITLE", "media" : "YOUR_MEDIA" }}' --accountId YOUR_ACCOUNT --depositYocto 6380000000000000000000
```
- [how to customize your metadata](https://github.com/near/NEPs/blob/ea409f07f8/specs/Standards/NonFungibleToken/Metadata.md#interface)
- ``depositYocto`` can increase
