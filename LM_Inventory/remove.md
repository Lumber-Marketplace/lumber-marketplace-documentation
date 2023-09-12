# Remove Inventory:

## Summary

This endpoint is used to remove bundels from a businesses inventory (due to in-pserson sales, disassembling of bundles, etc.)

---

## Request

`DELETE:` `https://inbound.lumbermarketplace.com/inventory/{YardMaster-API-Key}`

---

## Example Data:

```json
[
    {
        "yardid": "1",
        "bundleid": "100429"
    },
    {
        "yardid": "1",
        "bundleid": "100430"
    }
]
```

## Response

```json
[
    {
        Good

        Error: uuid invalid

        Error: Could not locate Bundle:[bundleid] on Yard: [yardid] (multiple)
         - If this is new inventory needs to be sent to the inventory endpoint

        Error: attribute miss-match (multiple)
         - Fix attribute X

        Error: attribute missing (multiple)
         - required attribute x is missing from the data

        Error: part of an load
         - matching bundleid and yardid is currently part of a load and cannot be updated

         Error: part of an order
         - matching bundleid and yardid is currently part of an order and cannot be updated

        Error: yardid miss-match (multiple)
         - User needs to log into LM and add [yardid] to shipping address
    }
]
```
