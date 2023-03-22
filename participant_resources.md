### CryptoWorkspace
- https://cryptoworkspace.li/
- Each participant will receive a login code

### BIP-85
- What is BIP-85: https://github.com/bitcoin/bips/blob/master/bip-0085.mediawiki
- https://getcoinplate.com/bip39-seed-phrase-mnemonics-generator-offline-online-tool/
- ![image](https://user-images.githubusercontent.com/2338287/225087206-40273f92-dfe8-469b-b396-01ebd3eab84e.png)

### Bitcoin Value Assert
- https://github.com/Blockfinance-ECO/Bitcoin-Value-Assert 
- Watch a video on how to use it: https://www.youtube.com/watch?v=Gyy8i1_MRIs 

### Bitcoin node
- https://bitcoin.org/en/full-node#initial-block-downloadibd
- https://bitcoin.org/en/download
- https://jlopp.github.io/bitcoin-core-config-generator/
- https://developer.bitcoin.org/reference/rpc/
- https://bitcoindev.network/bitcoin-script-101/

### General bitcoin resources
- https://github.com/bitcoinbook/bitcoinbook
- 

### Bitcoin Payment Server
- https://btcpayserver.org/


## Bitcoin Infrastructure
When connected to the Network-Box of Blockfinance ECO AG via Cable or Wifi.
To get better speeds, connect via network cable.

### How to connect to the Blockfinance Bitcoin Network?

### Via network Cable:
Just plug in the network cable to your Laptop and you will get an IP address via DHCP.

### Via WiFi

#### 2G-Wifi
SSID: BlockfinanceECO-CrypotWorkspace
Password: ask operator

#### 5G-Wifo
SSID: BlockfinanceECO-CrypotWorkspace
Password: ask operator

###  Internal IP Addresses

#### NAS01
To get all your needed Blockchain files visit NAS01 at:

- https://10.20.20.10/ or
- https://nas01.bfeco.local/

User: bfeco
Pass: bfeco123
Domain: WORKGROUP

### Mount via Console

#### NFS
Multiple users

```sudo apt update
sudo apt install nfs-common
```
`showmount -e 10.20.20.10` 
oder 
`showmount -e nas01.bfeco.local`

**Create a directory to mount a copy of bitcoin blockchain:**

`sudo mkdir /mnt/bitcoind`

**Mount the NFS share with a copy of Bitcoin Blockchain**

`sudo mount -t nfs 10.20.20.10:/BFECO-Bitcoin /mnt/bitcoind`

**now copy the Bitcoin blockchain to your local harddisk:**

`sudo rsync -av --info=progress2 /mnt/bitcoind/ /opt/`

**now unmount the directory let other usery sync as well:**

`sudo umount /mnt/bitcoind`

**Once you did copy the blockchain you can then run `bitcoin-qt` or `bitcoind`:**

`sudo chown -R oem:oem /opt/*` (run this once to correct file and folder access) 

`/opt/bitcoind/bin/bitcoin-qt -datadir=/opt/bitcoind/data/ `



