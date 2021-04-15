# clone the frontier chain repo
git clone git@github.com:frontierdotxyz/frontier-chain.git

# install
cd frontier-chain && git checkout v0.1.0 && make install

# initialize chain
frontd init my_node --chain-id frontier-chain-testnet-0-black-mamba

# Add validator key
frontcli config keyring-backend test

frontcli keys add validator

 {  
   "name": "validator",  "type": "local",  "address":       "front16r9u60nej38edv475nyu45sj8wnhkaypkgdcgc",  "pubkey": "frontpub1addwnpepqtx2eqzd4djk8c3nwfunpru28k33k0e8p472ng0ulc353jmdnmy2g84jvjk",  "mnemonic": "predict forum edit parent biology budget galaxy uphold cherry crater denial key amused battle inside you list network agree sure vibrant reveal engage faith"
}

frontd add-genesis-account $(frontcli keys show validator -a) 1000000000000front

frontd gentx --name validator --amount 1000000000000front --keyring-backend test

