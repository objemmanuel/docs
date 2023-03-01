# sendToAddressByAccount :: Qitmeer Documentation

### wallet\_sendToAddressByAccount <a href="#wallet_sendtoaddressbyaccount" id="wallet_sendtoaddressbyaccount"></a>

send passed amount using specific account

#### NOTE <a href="#note" id="note"></a>

* This function requires to the wallet to be unlocked. See wallet\_unlock
* The amount cannot exceed 21,000,000

#### Parameters <a href="#parameters" id="parameters"></a>

1. `accountName: (string)` from account
2. `addressStr: (string)` to address
3. `amount: (numeric)` send amount coin
4. `comment: (string)` not used, reserved for future use
5. `commentTo: (string)` not used, reserved for future use

#### Returns <a href="#returns" id="returns"></a>

**Success**

`TxID: (hex string)` the TxID for the created transaction

**Error**

`-32000`

1. `-13` Enter the wallet passphrase with walletpassphrase first
2. `-32603` transaction output amount exceeds maximum value
3. `-32603` balance is not enough,please deduct the service charge

#### Example <a href="#example" id="example"></a>

**Request**

```
$  curl -sk -u "test:test" -X POST -H 'Content-Type: application/json' --data '{"jsonrpc":"1.0","method":"wallet_sendToAddressByAccount","params":["test", "Tmb1dCAB8ixNC6d2VtdCYZuhXBVPbnRVi7y", 0.999, "MEER", "", ""],"id":1}' http://127.0.0.1:8130/api |jq .
```

**Response**

```
{
  "jsonrpc": "2.0",
  "id": 1,
  "result": "cfd933e4590a3cfbcf94e9220c77834fe8a869414c51e3bd0ce5af23592e80f9"
}
```
