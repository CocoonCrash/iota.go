# ExtractJSON()
ExtractJSON extracts a JSON string from the given transactions. It supports JSON messages in the following format:  - "{ \"message\": \"hello\" }"  - "[1, 2, 3]"  - "true", "false" and "null"  - "hello"  - 123
> **Important note:** This API is currently in Beta and is subject to change. Use of these APIs in production applications is not supported.


## Input

| Parameter       | Type | Required or Optional | Description |
|:---------------|:--------|:--------| :--------|
| txs | Transactions | true | The Transactions from which to derive the JSON message from.  |




## Output

| Return type     | Description |
|:---------------|:--------|
| string | The JSON value. |
| error | Returned for invalid messages. |




## Example

```go
func ExampleExtractJSON() 
	var bundleWithJSONMsg = bundle.Bundle{
		{
			Hash:                          "IPQYUNLDGKCLJVEJGVVISSQYVDJJWOXCW9RZXIDFKMBXDVZDXFBZNZJKBSTIMBKAXHFTGETEIPTZGNTJK",
			// JSON object is contained within the message fragment
			SignatureMessageFragment:      "ODEALAPCLAEADBEALAQCLAQAEALARCLADBEALASCLAQAEALATCLADBEALAHAPCGDSCUCSCIBIALAEAQD9999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999999",
			Address:                       "A9RGRKVGWMWMKOLVMDFWJUHNUNYWZTJADGGPZGXNLERLXYWJE9WQHWWBMCPZMVVMJUMWWBLZLNMLDCGDJ",
			Value:                         0,
			ObsoleteTag:                   "BIGTEST99999999999999999999",
			Tag:                           "999999999999999999999999999",
			Timestamp:                     1482522289,
			CurrentIndex:                  0,
			LastIndex:                     0,
			Bundle:                        "TXEFLKNPJRBYZPORHZU9CEMFIFVVQBUSTDGSJCZMBTZCDTTJVUFPTCCVHHORPMGCURKTH9VGJIXUQJVHK",
			TrunkTransaction:              "999999999999999999999999999999999999999999999999999999999999999999999999999999999",
			BranchTransaction:             "999999999999999999999999999999999999999999999999999999999999999999999999999999999",
			AttachmentTimestamp:           -1737679689424,
			AttachmentTimestampLowerBound: -282646045775,
			AttachmentTimestampUpperBound: 2918881518838,
			Nonce:                         "999999999999999999999999999999999999999999999999999999999999999999999999999999999",
		},
	}

	jsonMsg, err := transaction.ExtractJSON(bundleWithJSONMsg)
	if err != nil {
		// handle error
		return
	}
	fmt.Println(jsonMsg)
	// output: "{ 'a' : 'b', 'c': 'd', 'e': '#asdfd?$' }"
}

```