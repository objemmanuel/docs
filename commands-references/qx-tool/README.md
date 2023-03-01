# Qx Tool

## QX TOOLS

### Qx user guide <a href="#qx-user-guide" id="qx-user-guide"></a>

[Qx](https://github.com/Qitmeer/qx) is a command-line tool that provides a variety of commands for key management and transaction construction, such as random “seed” generation, public/private key encoding etc. qx cab be built and distributed as a single file binary, which works like the swiss army knife of qitmeer.

Please see more details at [https://github.com/Qitmeer/qx](https://github.com/Qitmeer/qx)

### Prerequisites <a href="#prerequisites" id="prerequisites"></a>

Update Go to version at least 1.12 (required >= **1.12**)

Check your golang version

```bash
~ go version
go version go1.12 darwin/amd64
```

### How to build <a href="#how-to-build" id="how-to-build"></a>

```bash
~ mkdir -p /tmp/work
~ cd /tmp/work
~ git clone https://github.com/Qitmeer/qx.git
~ cd qx
~ go build
~ ./qx --version
Qx Version : "0.0.1"
```

### qx Commands <a href="#qx-commands" id="qx-commands"></a>

```bash
~ qx

Usage: qx [--version] [--help] <command> [<args>]

encode and decode :
    base58-encode         encode a base16 string to a base58 string
    base58-decode         decode a base58 string to a base16 string
    base58check-encode    encode a base58check string
    base58check-decode    decode a base58check string
    base64-encode         encode a base16 string to a base64 string
    base64-decode         decode a base64 string to a base16 string
    rlp-encode            encode a string to a rlp encoded base16 string
    rlp-decode            decode a rlp base16 string to a human-readble representation

hash :
    blake2b256            calculate Blake2b 256 hash of a base16 data.
    blake2b512            calculate Blake2b 512 hash of a base16 data.
    sha256                calculate SHA256 hash of a base16 data.
    sha3-256              calculate SHA3 256 hash of a base16 data.
    keccak-256            calculate legacy keccak 256 hash of a bash16 data.
    blake256              calculate blake256 hash of a base16 data.
    ripemd160             calculate ripemd160 hash of a base16 data.
    bitcion160            calculate ripemd160(sha256(data))
    hash160               calculate ripemd160(blake2b256(data))

entropy (seed) & mnemoic & hd & ec
    entropy               generate a cryptographically secure pseudorandom entropy (seed)
    hd-new                create a new HD(BIP32) private key from an entropy (seed)
    hd-to-ec              convert the HD (BIP32) format private/public key to a EC private/public key
    hd-to-public          derive the HD (BIP32) public key from a HD private key
    hd-decode             decode a HD (BIP32) private/public key serialization format
    hd-derive             Derive a child HD (BIP32) key from another HD public or private key.
    mnemonic-new          create a mnemonic world-list (BIP39) from an entropy
    mnemonic-to-entropy   return back to the entropy (the random seed) from a mnemonic world list (BIP39)
    mnemonic-to-seed      convert a mnemonic world-list (BIP39) to its 512 bits seed.
    ec-new                create a new EC private key from an entropy (seed).
    ec-to-public          derive the EC public key from an EC private key (the compressed format by default )
    ec-to-wif             convert an EC private key to a WIF, associates with the compressed public key by default.
    wif-to-ec             convert a WIF private key to an EC private key.
    wif-to-public         derive the EC public key from a WIF private key.

addr & tx & sign
    ec-to-addr            convert an EC public key to a paymant address. default is qx address
    tx-encode             encode a unsigned transaction.
    tx-decode             decode a transaction in base16 to json format.
    tx-sign               sign a transactions using a private key.
    msg-sign              create a message signature
    msg-verify            validate a message signature
```

**Qx Generate address by mnemonic**

```bash
# create qitmeer mainnet address by mnemonic
~ echo "dune school cash fancy post theory sense again earth divide balcony always"|qx mnemonic-to-seed | qx ec-new |qx ec-to-public|qx ec-to-addr

# qng address
MmVipyQydGr6xN3qNkwBS48fzENUAYmnTZh
```

**KAHF Generate qng address by mnemonic**

```bash
# import new wallet with mnemonic
~ dune school cash fancy post theory sense again earth divide balcony always
```

[![kahf-qng-wallet](https://qitmeer.github.io/docs/en/reference/qxtools/wallet/kahf.jpeg)](https://qitmeer.github.io/docs/en/reference/qxtools/wallet/kahf.jpeg)

**Qx Generate evm bip44 address by mnemonic**

```bash
# create qitmeer mainnet address by mnemonic
~ echo "dune school cash fancy post theory sense again earth divide balcony always"|qx mnemonic-to-seed|qx hd-new -v bip32|qx hd-derive -v bip32 -p "m/44'/60'/0'/0/0"|qx hd-to-ec -v bip32|qx ec-to-public|qx ec-to-ethaddr

# qng evm | eth | bsc address
0x2cb3aD95bE524F9d34E17Da37a901F63fa12Ba35
```

**KAHF Generate evm bip44 address by mnemonic**

```bash
# import new wallet with mnemonic
~ dune school cash fancy post theory sense again earth divide balcony always
```

[![kahf-qng-wallet](https://qitmeer.github.io/docs/en/reference/qxtools/wallet/eth.jpeg)](https://qitmeer.github.io/docs/en/reference/qxtools/wallet/eth.jpeg)[![kahf-qng-wallet](https://qitmeer.github.io/docs/en/reference/qxtools/wallet/bsc.jpeg)](https://qitmeer.github.io/docs/en/reference/qxtools/wallet/bsc.jpeg)[![kahf-qng-wallet](https://qitmeer.github.io/docs/en/reference/qxtools/wallet/evm.jpeg)](https://qitmeer.github.io/docs/en/reference/qxtools/wallet/evm.jpeg)

&#x20;
