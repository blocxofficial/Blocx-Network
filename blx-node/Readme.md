# How Run a BLX Validator

## Setting up a node

1. Head to BlocX's Official Github

2. Clone https://github.com/BlocXOfficial/BlocX-Network.git

3. Copy source form node-example to root folder

```
cp -r BlocX-Network/blx-node/BLX  /root/
```

4. Create your own account

```
cd /root/BLX
chmod +x openethereum
./openethereum account new --config nodes/validator/node.toml
```

5. You will get a returned answer. Example : address 0x9dACbC430f0b7e4b5078cdb583b4ec6175b004Fc

6. Copy the result that you received, which is your account address to the node.toml file.


```
//insert your account address

...
[account]
unlock = ["insert your account address"]
password = ["password"]

[mining]
force_sealing = true
engine_signer = "insert your account address"
reseal_on_txs = "none"
...

```

7. Run the authority nodes

```
./openethereum --config ./nodes/validator/node.toml

```

8. Stake

   BlocX Mainnet is using a Proof of Stake consensus protocol. This means you will have to stake your BLX Coins. 
   First step to stake : Send your BLX coins to the BlocX Mainnet Consensus contract address from the validator address. The BlocX Consensus contract address: 

   0xD4dfc7572FAC4B92c3Dccebafd5C11C0d587bfA4 

   The best way to conduct this is to import your private key JSON file (UTC-xxx) or key-store file to your preferred wallet (for example Metamask)
   Change the network to BLX Mainnet by connecting to our RPC Network Found here : https://docs.blocxchain.org/introduction/connect-blocx-mainet

   Once connected send the BLX coin to the Consensus contract address.

   You can find your key-store (containing your private key) and the password for the account that was created in step 4 above.

   /BLX/nodes/validator/keys/BLX/UTC--xxxx 

   /BLX/nodes/validator/node.pwd

10. There will be a 24 - 48 hour wait as Next Cycle will start to conduct.
