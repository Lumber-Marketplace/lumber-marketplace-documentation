# Remove Inventory:

## Summary

This endpoint is used to update bundels in a businesses inventory. Any objects included will be updated on the bundle. This will only overwrite objects that are included. Any missing objects will not be updated.

_Note: any objects with an empty string will be replaced with the empty string value._

---

## Request

`POST:` `https://inbound.lumbermarketplace.com/staging/inventory/update/{business-uuid}`

## Example Data:

```json
[
    {
        "bundletype": "export",
        "yardid": "1",
        "bundleid": "100429",
        "status": "available",
        "speciesid": "Ash",
        "thknum": "6",
        "thkden": "4",
        "gradeid": "#2C",
        "moistureid": "Kiln Dried",
        "finishid": "S2S",
        "region": "Appalachian",
        "averagelength": "9.7",
        "averagewidth": "6.6",
        "length1": "9",
        "length2": "10",
        "length3": "0",
        "length4": "0",
        "length5": "0",
        "pieces": "103",
        "boardfeet": "828",
        "datecreated": "8/15/2011",
        "layers": "",
        "weight": "",
        "detail": [
            {
                "gradeid": "#2C",
                "length": "9",
                "width": "4",
                "surfacemeasure": "3",
                "pieces": "1"
            },
            {
                "gradeid": "#2C",
                "length": "9",
                "width": "6",
                "surfacemeasure": "4.5",
                "pieces": "17"
            },
            {
                "gradeid": "#2C",
                "length": "9",
                "width": "7",
                "surfacemeasure": "5.25",
                "pieces": "9"
            },
            {
                "gradeid": "#2C",
                "length": "9",
                "width": "8",
                "surfacemeasure": "6",
                "pieces": "2"
            },
            {
                "gradeid": "#2C",
                "length": "9",
                "width": "9",
                "surfacemeasure": "6.75",
                "pieces": "1"
            },
            {
                "gradeid": "#2C",
                "length": "10",
                "width": "4",
                "surfacemeasure": "3.33333333333333",
                "pieces": "2"
            },
            {
                "gradeid": "#2C",
                "length": "10",
                "width": "5",
                "surfacemeasure": "4.16666666666667",
                "pieces": "2"
            },
            {
                "gradeid": "#2C",
                "length": "10",
                "width": "6",
                "surfacemeasure": "5",
                "pieces": "45"
            },
            {
                "gradeid": "#2C",
                "length": "10",
                "width": "7",
                "surfacemeasure": "5.83333333333333",
                "pieces": "14"
            },
            {
                "gradeid": "#2C",
                "length": "10",
                "width": "8",
                "surfacemeasure": "6.66666666666667",
                "pieces": "2"
            },
            {
                "gradeid": "#2C",
                "length": "10",
                "width": "9",
                "surfacemeasure": "7.5",
                "pieces": "2"
            },
            {
                "gradeid": "#2C",
                "length": "10",
                "width": "10",
                "surfacemeasure": "8.33333333333333",
                "pieces": "2"
            },
            {
                "gradeid": "#2C",
                "length": "10",
                "width": "12",
                "surfacemeasure": "10",
                "pieces": "3"
            },
            {
                "gradeid": "#2C",
                "length": "10",
                "width": "13",
                "surfacemeasure": "10.8333333333333",
                "pieces": "1"
            }
        ]
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
