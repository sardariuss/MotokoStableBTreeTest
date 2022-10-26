# MotokoStableBTreeTest
Tests on the motoko stable BTree using the actual stable memory.

### Rational

The Motoko tests defined in the MotokoStableBTree source code use a VecMemory, which is a simple buffer of bytes (hence not stable).
This VecMemory is used to be able to test the BTree itself; one has not choice but to use a not stable memory inside test modules, because the stable memory can only be used in a canister.
This additional test repository performs tests on the MotokoStableBTree inside a canister, using the actual stable memory.

### Requirements

dfx, npm, vessel, ic-repl

### Install

```sh
vessel install
npm install
```

### To run the multiple insertion test (in js)

```sh
dfx canister deploy test --argument='(record {max_key_size=32; max_value_size=128})'
node test.js
```

### To run the upgrade test (in ic-repl)

```sh
./test.sh
```
