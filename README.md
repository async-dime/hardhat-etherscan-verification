# Simple Smart Contract Verification with Hardhat & Etherscan

first, run

```shell
npx hardhat compile
```

```shell
npm run mumbai
```

output:

```sh
> hardhat-ver@1.0.0 mumbai
> npx hardhat run scripts/deploy.js --network mumbai

Verify Contract Address: <DEPLOYED_CONTRACT_ADDRESS>
Sleeping.....
Nothing to compile
NomicLabsHardhatPluginError: Failed to send contract verification request.
Endpoint URL: https://api-testnet.polygonscan.com/api
Reason: The Etherscan API responded that the address <DEPLOYED_CONTRACT_ADDRESS> does not have bytecode.
This can happen if the contract was recently deployed and this fact hasn't propagated to the backend yet.
Try waiting for a minute before verifying your contract. If you are invoking this from a script,
try to wait for five confirmations of your contract deployment transaction before running the verification subtask.
```

So, I wait a couple of minutes and run:

```shell
npx hardhat verify --mumbai <DEPLOYED_CONTRACT_ADDRESS>
```

output:

```sh
Nothing to compile
Successfully submitted source code for contract
contracts/Verify.sol:Verify at <DEPLOYED_CONTRACT_ADDRESS>
for verification on the block explorer. Waiting for verification result...

Successfully verified contract Verify on Etherscan.
https://mumbai.polygonscan.com/address/<DEPLOYED_CONTRACT_ADDRESS>#code
```
