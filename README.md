# Blockchain-goquorum
cd network/3-nodes-raft-tessera-bash
./start.sh
Sending a private transaction
Send an example private contract from Node 1 to Node 2 (this is denoted by Node 2’s public key passed via privateFor: ["QfeDAys9MPDs2XHExtc84jKGHxZg/aj52DTh0vtA3Xc="] in private-contract.js):


./runscript.sh private_contract.js
Take note of the TransactionHash printed to the terminal.

Inspecting the GoQuorum nodes
You can inspect any of the GoQuorum nodes by using ./attach.sh to open the geth JavaScript console. For this demo, you will be inspecting Node 1, Node 2, and Node 3.

It is recommended to use separate terminal windows for each node you are inspecting. In each terminal, ensure you are in your network’s directory, then:

In terminal 1 run ./attach.sh 1 to attach to node 1
In terminal 2 run ./attach.sh 2 to attach to node 2
In terminal 3 run ./attach.sh 3 to attach to node 3
To look at the private transaction that was just sent, run the following command in one of the terminals:
eth.getTransaction("your hush")
where you should replace this hash with the TransactionHash that was previously printed to the terminal. This will print a result of the form:


{
  blockHash: "0x4d6eb0d0f971b5e0394a49e36ba660c69e62a588323a873bb38610f7b9690b34",
  blockNumber: 1,
  from: "0xed9d02e382b34818e88b88a309c7fe71e65f419d",
  gas: 4700000,
  gasPrice: 0,
  hash: "0xe28912c5694a1b8c4944b2252d5af21724e9f9095daab47bac37b1db0340e0bf",
  input: "0x58c0c680ee0b55673e3127eb26e5e537c973cd97c70ec224ccca586cc4d31ae042d2c55704b881d26ca013f15ade30df2dd196da44368b4a7abfec4a2022ec6f",
  nonce: 0,
  r: "0x4952fd6cd1350c283e9abea95a2377ce24a4540abbbf46b2d7a542be6ed7cce5",
  s: "0x4596f7afe2bd23135fa373399790f2d981a9bb8b06144c91f339be1c31ec5aeb",
  to: null,
  transactionIndex: 0,
  v: "0x25",
  value: 0
}

for more info https://docs.goquorum.consensys.net/en/stable/
