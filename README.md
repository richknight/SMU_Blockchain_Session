# SMU_Blockchain_Session
SMU Blockchain session on 20th Feb from 10:30am to 12:00pm

<h4> Deploying to local environment </h4>

1. Setup Truffle - https://azuremarketplace.microsoft.com/en-us/marketplace/apps/consensys.truffle 

2. Record the IP address of the Truffle VM; SSH to this IP address and run “testrpc”

3. Open another SSH window to the Truffle VM and do the following:

  a. mkdir first_project  # Create a folder for your new dapp

  b. cd first_project  # Move into that folder

  c. truffle init    # Initialize a default truffle project in that folder

  d. truffle compile # Compile the existing smart contracts

  e. truffle migrate  # Publish the dapp on the blockchain

4. Install the Metamask plugin in Chrome - https://metamask.io/ 

5. Point Metamask to testrpc endpoint setup previously using http://TruffleVM_IP:8545

6. Log into Metamask and see the first account

7. Transfer between first testrpc account and Metamask account using CURLcurl -d '{"jsonrpc":"2.0","method":"eth_sendTransaction","params": [{"from":"0x0f91747e3a5df28d81ab30b2d8216c93263c0cf3", "to":"0xbbd220f66e989a493c4d48531ea1e283abc385de", "value": 1e18}], "id":1}' -X POST http://localhost:8545/

8. Load Metamask with TESTRPC Mnemonic

9. Transfer between accounts using Metamask

<h4>Deploying to Private Blockchain on Microsoft Azure</h4>

1. Setup an Ethereum Enterprise private consortium template - https://azuremarketplace.microsoft.com/en-us/marketplace/apps/microsoft-azure-blockchain.azure-blockchain-service?tab=Overview 

2. Open an SSH window to the Truffle VM and do the following:

  a. mkdir second_project  # Create a folder for your new dapp

  b. cd second_project  # Move into that folder

  c. truffle init    # Initialize a default truffle project in that folder

  d. modify truffle.js to point to the Ethereum Enterprise private consortium template

  e. Unlock the default geth account by opening an SSH window the Ethereum Enterprise private consortium template’s transaction node using: 
  personal.unlockAccount("0x04e2e303405c4e925c2708ac2ccfe86ded44df77", "Microsoft12345", 15000)

  f. truffle compile # Compile the existing smart contracts

  g. truffle migrate  # Publish the dapp on the blockchain

  h. truffle build   # Compile the dapp

  i. truffle serve   # Host your web interface on port 8080

3. Open the Distributed App using http://TruffleVM_IP:8080

4. Restart Metamask to point to the Ethereum Enterprise private consortium template’s RPC endpoint



















