# submitBlock :: Qitmeer Documentation

#### SubmitBlock <a href="#submitblock" id="submitblock"></a>

Attempts to submit new block to network.

**Parameters**

1. `hexBlock: (string)` hex-encoded block data to submit. Refer to [https://github.com/qitmeer/qitmeer-miner](https://github.com/qitmeer/qitmeer-miner) to investigate how to construct a block

**Returns**

**`(string)` submit message**

**Example**

**Request**

```
curl --data '{"method":"submitBlock","params":["0b0000009b324c447c093502bd2928251c7a76bd66fac662f4535130c512a52ff27c9ac291db77e47c8b7fb1199192e813698abd42ceae44c6f6cd7bb3bfee442b105079000000000000000000000000000000000000000000000000000000000000000000000000d998195eba6acfb00118539c0100c3b203006b871000627a170066122400e7a933007cfb3b00ed393d00b9a63e00fcad4d0083c954004b6c5c007ac77300db1b7a0025f27c00540e7d0015018300a40084000bc28900d0f38f002b8592007e759300195a9900a2529b002356a1004b86a2008affb300f5a3ba001b05bb00dc52bf006528c1008fa1c20058a4c8000ca3cc002ff1cc00e4e8d10052cfd400e063dd00612fdf007a7ee5001d93ea00c093fc00019b324c447c093502bd2928251c7a76bd66fac662f4535130c512a52ff27c9ac2010100000001b3e2498b9592e6871e1a02a23a32988495b0c3da449f1cb3f1389013d044713bffffffffffffffff01007841cb020000001976a914a6b8fe2348fad076b7fd1b34b7e5b35db96dc2a088ac000000000000000001455a08ec92282d01baa3be153131333933333038383330373933383831353235322435633739303233612d653130642d343631622d613438662d356563343961316233353330"],"jsonrpc":"2.0","id":1}' -s -k -u "test:test"  -H 'Content-Type: application/json' http://127.0.0.1:38131 |jq .
```

**Response**

```
"Block submitted accepted  hash fcd2fe6a284e46d4fb7893e84bbcc58ca96e020be1e57b5c1b2c45929cca8dee, height 10, order 10 amount 12000000000"
```
