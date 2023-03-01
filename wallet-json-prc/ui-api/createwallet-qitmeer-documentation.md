# createWallet :: Qitmeer Documentation

### ui\_createWallet <a href="#ui_createwallet" id="ui_createwallet"></a>

create wallet by seed

#### Parameters <a href="#parameters" id="parameters"></a>

1. `seed: (string)` seed
2. `walletPass: (string)` wallet password
3. `unlockPass: (string)` unlock password

#### Returns <a href="#returns" id="returns"></a>

**Success**

`null`

**Error**

`-32000` wallet exist

#### Example <a href="#example" id="example"></a>

**Request**

```
 curl -sku "test:test" -X POST -H 'Content-Type: application/json' --data '{"jsonrpc":"1.0","method":"ui_createWallet","params":["0d82f3214e900c039c8e05c04bef5f22bdf5804344e69e8f7426e90fabb0eb178a8c4f99850c77be09f609b7145799fb0772c1c0c1087acd55868240755a437a", "walletPass", "unlockPass"],"id":1}' http://127.0.0.1:8130/api | jq
```

**Response**

```
{
  "jsonrpc": "2.0",
  "id": 1,
  "result": null
}

```
