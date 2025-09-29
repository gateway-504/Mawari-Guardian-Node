# MAWARI Testnet Node

## Requirements: 
- **CPU**: 2 Dedicated vCPU with preferably 3GHz+ clock speed
- **Memory**: 4 GB RAM  
- **Disk**: 100 GB HDD or higher
- **Bandwidth**: 800Mbps or higher
- **Open TCP Ports**: 8231, 8085, 9864
- **Open UDP Ports**: 7621
  
## Preparation

- Claim faucet at https://hub.testnet.mawari.net/

- Mint 3 Guardians NFT at https://testnet.mawari.net/mint

## Setup on your terminal

- Install docker https://docs.docker.com/engine/install/ (skip if already installed)

- Set image name
- 
  
```
export MNTESTNET_IMAGE=us-east4-docker.pkg.dev/mawarinetwork-dev/mwr-net-d-car-uses4-public-docker-registry-e62e/mawari-node:latest
```


- Set address


```
export OWNER_ADDRESS=your_wallet
```


Replace your_wallet with the address used to mint the NFT earlier

- Create screen session


```
screen -S mawari
```


- Run the node


```
mkdir -p ~/mawari && docker run --pull always -v ~/mawari:/app/cache  -e OWNERS_ALLOWLIST=$OWNER_ADDRESS $MNTESTNET_IMAGE
```


Logs will appear like below:


```
2025-09-09T13:54:16.086Z    [INFO]    loaded config    {"config": {"network": "ethereum", "heartbeatPeriodSeconds": 
2025-09-09T13:54:16.086Z    [DEBUG]    initializing node ...
2025-09-09T13:54:16.088Z    [DEBUG]    generating burner wallet
2025-09-09T13:54:16.090Z    [DEBUG]    node cache does not exit, initializing empty node cache
2025-09-09T13:54:16.098Z    [DEBUG]    burner wallet cache written    {"file": "/app/cache/flohive-cache.json"}
2025-09-09T13:54:16.098Z    [DEBUG]    generated burner wallet    {"address": "<your burner wallet appears here>"}
2025-09-09T13:54:16.102Z    [INFO]    Using burner wallet    {"address": "<your burner wallet appears here>"}
Find and save the Burner wallet for delegation
```


- Send 1.1 mawari token to the Burner wallet above

- Detach screen: ctrl a + d

## Node Activation

 - Go to https://app.testnet.mawari.net/ and connect wallet

- Select all IDs, then click 'Delegate', enter the burner/operator wallet address in the available field, and confirm by clicking 'Delegate' again.

- Confirm in wallet

- Wait and check node status on the website

## DONE

