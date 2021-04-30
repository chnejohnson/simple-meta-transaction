# Simple Meta_Transactions

## Guild
### Step 1: Run Hardhat Network
Terminal in the folder of **token_contracts**

- `yarn` to install dependencies
- `npx hardhat node` to run hardhat network and JSON-RPC server at http://127.0.0.1:8545
- `npx hardhat run --network localhost scripts/deployMetaTransaction.js` to deploy meta-transaction contract

### Step 2: Run Relay Server
Terminal in the folder of **relay-server**

- `yarn` to install dependencies.
- `node main.js` to run app listening at http://localhost:3000

Open browser and go to http://localhost:3000, you can see:
```
Owner ETH balance: 9999.976306008
Owner Token balance: 2800
addr1 ETH balance: 10000.0
addr1 Token balance: 100
addr2 ETH balance: 10000.0
addr2 Token balance: 100
```

### Step 3: Run frontend
Terminal in the folder of **wallet-vue**

- `yarn` to install dependencies.
- `npx vue-cli-service serve` to run frontend app at http://localhost:8080
- Open browser and devtool **console**.
- At your MetaMask wallet, import one (or two) dev account(s) in hardhat network:

```
Account #1: 0x70997970c51812dc3a010c7d01b50e0d17dc79c8 (10000 ETH)
Private Key: 0x59c6995e998f97a5a0044966f0945389dc9e86dae88c7a8412f4603b6b78690d

Account #2: 0x3c44cdddb6a900fa2b585dd299e03d12fa4293bc (10000 ETH)
Private Key: 0x5de4111afa1a4b94908f83103eb1f1706367c2e68ca870fc3fb9a804cdab365a
```

- You can use Rinkeby or any testnet to interact with dapp.
- Use addr1 account with metamask and reload page to see the right account **data** in the browser console.
- fill in the input boxes about "to" address and "amount".
- press "sign" to sign the transaction, and you can see signature both on the page and console.
- press "transfer", and you can see "signature sent" in the console.


Go to http://localhost:3000 on browser and then you can see addr1 transfer tokens to addr2 without gas fee which is paid by owner.
```
Owner ETH balance: 9999.975866904
Owner Token balance: 2800
addr1 ETH balance: 10000.0
addr1 Token balance: 58
addr2 ETH balance: 10000.0
addr2 Token balance: 142
```