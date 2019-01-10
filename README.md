# ProtoChain

A prototype blockchain based on [Substrate](https://github.com/paritytech/substrate).

## Rust toolchain

```
curl https://sh.rustup.rs -sSf | sh
rustup update nightly
rustup target add wasm32-unknown-unknown --toolchain nightly
rustup update stable
cargo install --git https://github.com/alexcrichton/wasm-gc
```

## Build steps

```
./scripts/init.sh
./scripts/build.sh
cargo build
```

## Single node
* `protochain --dev` equals `protochain --chain=dev --validator --key Alice`

## Two nodes
* In terminal 1, `protochain --chain=local --validator --name "ALICE" --key Alice -d /tmp/alice --node-key 0000000000000000000000000000000000000000000000000000000000000001`
* In terminal 2, `protochain --chain=local --validator --name "BOB" --key Bob -d /tmp/bob --port 30334 --bootnodes '/ip4/127.0.0.1/tcp/30333/p2p/QmQZ8TjTqeDj3ciwr93EJ95hxfDsb9pEYDizUAbWpigtQN'`

## Web UI

```
git clone https://github.com/polkadot-js/apps.git
cd apps
yarn
yarn run start
```

* Access the UI via http://localhost:3000 (or use https://polkadot.js.org/apps/#/explorer)
* Settings -> general -> remote node/endpoint to connect: Local Node(127.0.0.1:9944) -> default interface theme: Substrate -> interface operation mode: Fully featured.
