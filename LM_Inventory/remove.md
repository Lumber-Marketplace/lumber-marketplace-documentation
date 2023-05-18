# Remove Inventory:

## Summary

This endpoint is used to remove bundels from a businesses inventory (due to in-pserson sales, disassembling of bundles, etc.)

---

## Request

`POST:` `https://inbound.lumbermarketplace.com/staging/inventory/remove/{business-uuid}`

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
        example response data
    }
]
```
