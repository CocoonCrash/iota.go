# C128ProofOfWork()
PoWC128 does Proof-of-Work on the given trytes using native C code and __int128 C type. This implementation follows common C standards and does not rely on SSE which is AMD64 specific.
> **Important note:** This API is currently in Beta and is subject to change. Use of these APIs in production applications is not supported.


## Input

| Parameter       | Type | Required or Optional | Description |
|:---------------|:--------|:--------| :--------|
| trytes | Trytes | false |   |
| mwm | int | false |   |
| parallelism |  | false |   |




## Output

| Return type     | Description |
|:---------------|:--------|
| Trytes |  |
| error |  |


