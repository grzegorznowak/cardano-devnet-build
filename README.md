# Cardano Devnet Container

Builds and distributes cardano devnet containers using helper projects

## Quickstart

```
# install podman https://podman.io/getting-started/installation

# then execute
podman run --name devnet1 ghcr.io/grzegorznowak/cardano-devnet:1.33.0

# wait for "Congrats! Your network is ready for use!"

# === in A NEW TERMINAL ===
# interact with the blockchain from the shell
podman exec devnet1 cardano-cli query utxo --whole-utxo --testnet-magic 42

# or just own the devnet1's bash 
podman exec -it devnet1 bash

# and operate on it directly from within
cardano-cli query utxo \
--address $(cat ~/cardano_devnet/private-testnet/addresses/user1.addr) \
--testnet-magic 42

# a killed devnet1 blockchain can be revived with
podman start devnet1

# create as many devnetX containers as you need, tweak, adjust to taste and prosper 
```

## Dependent projects

Useful scripts that help to set up local cardano blockchain:
https://github.com/woofpool/cardano-private-testnet-setup

Role used to install the cardano-node and cardano-cli binaries: 
https://github.com/grzegorznowak/cardano-node-role


