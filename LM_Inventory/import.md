# Import Inventory:

## Summary

This endpoint is used for the initial inventory import process.

**For any missing values, include the key and the value needs to be an empty string (example: `""`)**

---

## Bundle Schema:

| Key         | Type   | Required | Notes                                                                                     |
| ----------- | ------ | -------- | ----------------------------------------------------------------------------------------- |
| bundletype  | string | false    | Used in FS but not currently in LM. LM may use this in the future                         |
| yardid      | string | true     | If multiple, these must be set to shipping addresses in LM                                |
| bundleid    | string | true     | Bundle ID in FS.                                                                          |
| status      | string | true     | `active \ inactive \ removed`                                                             |
| speciesid   | string | true     | Must match LM [Species Attributes](attributes/species.md)                                 |
| thknum      | string | true     | Must match LM [Thickness Attributes](attributes/thickness.md) (numerator)                 |
| thkden      | string | true     | Must match LM [Thickness Attributes](attributes/thickness.md) (denominator)               |
| gradeid     | string | true     | Must match LM [Grade Attributes](attributes/grade.md)                                     |
| moistureid  | string | true     | Must match LM [Moisture Attributes](attributes/moisture.md)                               |
| finishid    | string | true     | Must match LM [Finish Attributes](attributes/finish.md)                                   |
| region      | string | true     | Must match LM [Region Attributes](attributes/region.md)                                   |
| length1     | string | true     | Must match LM [Length Attributes](attributes/length.md)                                   |
| length2     | string | false    | Must match LM [Length Attributes](attributes/length.md)                                   |
| length3     | string | false    | Must match LM [Length Attributes](attributes/length.md)                                   |
| length4     | string | false    | Must match LM [Length Attributes](attributes/length.md)                                   |
| length5     | string | false    | Must match LM [Length Attributes](attributes/length.md)                                   |
| pieces      | string | false    |                                                                                           |
| boardfeet   | string | true     |                                                                                           |
| datecreated | string | false    |                                                                                           |
| weight      | string | false    | Used for quoting shipping and load estimation. If not populated, LM calculates this value |
| detail      | array  | true     |                                                                                           |

## Bundle Detail Schema:

| Key            | Value  | Required | Notes                                                   |
| -------------- | ------ | -------- | ------------------------------------------------------- |
| gradeid        | string | false    | Must match LM [Grade Attributes](attributes/grade.md)   |
| length         | string | false    | Must match LM [Length Attributes](attributes/length.md) |
| width          | string | false    |                                                         |
| surfacemeasure | string | false    |                                                         |
| pieces         | string | false    |                                                         |

## Request

`POST:` `https://inbound.lumbermarketplace.com/inventory/{business-uuid}`

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
        Good

        Error: uuid invalid

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
