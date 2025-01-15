# bitcoin-core-docker

```
services:
  bitcoin-node:
    image: ruimarinho/bitcoin-core:latest
    container_name: bitcoin-node
    ports:
      - "8332:8332" # RPC Port
      - "8333:8333" # P2P Port
    volumes:
      - bitcoin-data:/root/.bitcoin
    environment:
      - BITCOIN_RPCUSER=yourrpcuser
      - BITCOIN_RPCPASSWORD=yourrpcpassword
      - BITCOIN_NETWORK=mainnet
      - BITCOIN_PRINTTOCONSOLE=1
      - BITCOIN_TXINDEX=1
    restart: unless-stopped

volumes:
  bitcoin-data:
    driver: local
```
