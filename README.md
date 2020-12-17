## WNN

WINNER public chain, strive to build a new digital asset transaction ecology.

1.Low Latency Block confirmation  
2.Smart contract platform powered by Ethereum  
3.Time Delay Security  
4.Hierarchical Role Based Permissions  
5.Support for Biometric Hardware Secured Keys (e.g. Apple Secure Enclave)  
6.Designed for Inter Blockchain Communication  

## Disclaimer

winner is neither launching nor operating any initial public blockchains based upon the WNN software. This release refers only to version 1.0 of our open source software. We caution those who wish to use blockchains built on WNN to carefully vet the companies and organizations launching blockchains based on WNN before disclosing any private keys to their derivative software.

## Operating Systems

WNN currently supports the following operating systems:  
CentOS 7  
Ubuntu 18.04  
MacOS 10.14 (Mojave)  

### Operating a private network

Maintaining your own private network is more involved as a lot of configurations taken for granted in
the official networks need to be manually set up.

#### Defining the private genesis state

First, you'll need to create the genesis state of your networks, which all nodes need to be aware of
and agree upon. This consists of a small JSON file (e.g. call it `genesis.json`):

```json
{
  "config": {
        "chainId": 0,
        "homesteadBlock": 0,
        "eip155Block": 0,
        "eip158Block": 0
    },
  "alloc"      : {},
  "coinbase"   : "0x0000000000000000000000000000000000000000",
  "difficulty" : "0x20000",
  "extraData"  : "",
  "gasLimit"   : "0x2fefd8",
  "nonce"      : "0x0000000000000042",
  "mixhash"    : "0x0000000000000000000000000000000000000000000000000000000000000000",
  "parentHash" : "0x0000000000000000000000000000000000000000000000000000000000000000",
  "timestamp"  : "0x00"
}
```

The above fields should be fine for most purposes, although we'd recommend changing the `nonce` to
some random value so you prevent unknown remote nodes from being able to connect to you. If you'd
like to pre-fund some accounts for easier testing, you can populate the `alloc` field with account
configs:

```json
"alloc": {
  "0x0000000000000000000000000000000000000001": {"balance": "111111111"},
  "0x0000000000000000000000000000000000000002": {"balance": "222222222"}
}
```

