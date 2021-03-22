# Teethereum Network Setup and Reboot

## Dependencies:
* Python v3.8.5
* Before running the blockchain you will need a way to send/store tokens and check transactions, we recommend: [MyCrypto.](https://download.mycrypto.com/)
* You will also need: [Go Ethereum Tools](https://geth.ethereum.org/downloads/) to run geth commands in your bash terminal.

## Account details
Nodes connect like so; Tooth3 => Tooth2 => Tooth1
* Tooth1 Address: 0x4342f90376F0215597B31189E72D322c50C226F5 (pre-funded)
* Tooth2 Address: 0x19fCa3fb941Cc3e581545d60D18666b19ed0b65d (RPC enabled)
* Tooth3 Address: 0x1eC2523AF832fBab96622c77BE17434ff102CeDF
* Password:	password123
## Node Reboot
To reboot the nodes:
1. In your bash, change directory to where the nodes are located.
2. Run this first command;
	* ./geth --datadir Tooth_1 --unlock "4342f90376F0215597B31189E72D322c50C226F5" --mine --miner.threads 1
	* Enter password and press enter
3. Repeat in another bash terminal with this command;
	* ./geth --datadir Tooth_2 --unlock "19fCa3fb941Cc3e581545d60D18666b19ed0b65d" --port 69 --rpc --bootnodes "enode://0363038d374c894b7f76f930a6d56d02cd15e7a43234ce42dbe807d171de993a745fae4481c9e2db190da17072910182dbd40b27a5c8d123bf3a5edf510b8200@127.0.0.1:30303" --ipcdisable --allow-insecure-unlock
4. Finally, in a third bash terminal run this command;
	* ./geth --datadir Tooth_3 --unlock "1eC2523AF832fBab96622c77BE17434ff102CeDF" --port 420 --bootnodes "enode://5fe8d16970550425850cfe5f0449b386645429f088b74315a57fd30e1a07d1fcd3c2c1e3078fecc51d7f879889d2c6cb73aaee4f73cc6a45d6237696d65b9ea9@127.0.0.1:69" --ipcdisable --allow-insecure-unlock

* -- datadir value: Data directory for the databases and keystore (default: "~/.ethereum")
* --unlock value: Comma separated list of accounts to unlock
* --mine: Enable mining
* --miner.threads value: Number of CPU threads to use for mining (default: 0)
* --port value: Network listening port (default: 30303)
* --bootnodes value: Comma separated enode URLs for P2P discovery bootstrap
* --ipcdisable: Disable the IPC-RPC server
* --allow-insecure-unlock: Allow insecure account unlocking when account-related RPCs are exposed by http
![](POA\ Development\ Chain/Screenies/teeth.png)
## Network configuration
![](POA\ Development\ Chain/Screenies/TeethereumConfig.png)
* Network Name: Teethereum
* Chain ID: 49
* Tooth1 Port: 30303
* Tooth2 Port: 69
* Tooth3 Port: 420
* password: password123

## Connecting MyCrypto to Teethereum
1. Create custom network making sure to point to the exposed RPC port (http://127.0.0.1:8545), using the same chain ID (49) and currency (ETH) and click save.
![](POA\ Development\ Chain/Screenies/change_network.png)
![](POA\ Development\ Chain/Screenies/node_setup.png)
2. Now open your wallet with your tooth1 keystore file located in the same directory and enter the password.
![](POA\ Development\ Chain/Screenies/keystore_file.png)
3. In the 'To Address' box type in the address of tooth2 and the amount you would like to send, hit send.
![](POA\ Development\ Chain/Screenies/address.png)
4. Click 'Check TX Status' to see if transaction is successful!
![](POA\ Development\ Chain/Screenies/check_tx_status.png)
![](POA\ Development\ Chain/Screenies/not_pending.png)

#### Thank you, stay hydrated.