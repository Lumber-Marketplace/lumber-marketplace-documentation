# Remove Inventory:

## Summary

This endpoint is used to update bundels in a businesses inventory.

_Note: The full bundle object is required for each bundle that needs to be updated in the inventory_

---

## Request

`PUT:` `https://inbound.lumbermarketplace.com/inventory/{YardMaster-API-Key}`

---

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

## Success Response

**Good**

```json
{
    "message": "Update request successful",
    "response": {
        "locations": {
            ...
        },
        "attributes": {
            ...
        },
        "inventory": {
            ...
        }
    },

}
```

## Error Responses

**Error: uuid invalid**

```json
{
  "message": "Error sending message to API",
  "error": {
    "statusCode": 400,
    "message": "Validation failed (uuid is expected)",
    "error": "Bad Request"
  }
}
```

**Error: Could not locate Bundle:[bundleid] on Yard: [yardid] (multiple)** - Currently it will add a new inventory if it is not found
*TODO*
- If this is new inventory needs to be sent to the inventory endpoint

**Error: attribute miss-match (multiple)** - Fix attribute X

```json
{
    "message": "Error sending message to API",
    "error": {
        "statusCode": 400,
        "message": "Some inventory items have errors",
        "error": "Bad Request",
        "data": [
            {
                "type": "inventory",
                "message": "These inventory items have errors.",
                "count": 1,
                "data": [
                    {
                        "type": "attribute",
                        "count": 1,
                        "data": [
                            {
                                "name": "032524",
                                "status": "AVAILABLE",
                                "weight": 0,
                                "businessId": 1,
                                "locationId": 2,
                                "attributes": [
                                            ...
                                ],
                                "details": {
                                            ...
                                }
                            }
                        ]
                    }
                ]
            },
            {
                "type": "attribute",
                "message": "These attributes are not connected to a site attribute.",
                "count": 1,
                "data": [
                    {
                        "apiName": "Ashs",
                        "type": "SPECIES",
                        "attributeId": 0
                    }
                ]
            }
        ]
    }
}
```

**Error: attribute missing (multiple)** - required attribute x is missing from the data

```json
         {
            "message": "Error sending message to API",
            "error": {
                "statusCode": 400,
                "message": "Some inventory items have errors",
                "error": "Bad Request",
                "data": [
                    {
                        "type": "inventory",
                        "message": "These inventory items have errors.",
                        "count": 1,
                        "data": [
                            {
                                "type": "attribute",
                                "count": 1,
                                "data": [
                                    {
                                        "name": "032524",
                                        "status": "AVAILABLE",
                                        "weight": 0,
                                        "businessId": 1,
                                        "locationId": 2,
                                        "attributes": [
                                                    ...
                                        ],
                                        "details": {
                                                    ...
                                        }
                                    }
                                ]
                            }
                        ]
                    },
                    {
                        "type": "attribute",
                        "message": "These attributes are not connected to a site attribute.",
                        "count": 1,
                        "data": [
                            {
                                "type": "SPECIES",
                                "attributeId": 0
                            }
                        ]
                    }
                ]
            }
        }
```

**Error: yardid miss-match (multiple)** - User needs to log into LM and add [yardid] to shipping address

```json
    {
        "message": "Error sending message to API",
    "error": {
        "statusCode": 400,
        "message": "Some inventory items have errors",
        "error": "Bad Request",
        "data": [
            {
                "type": "inventory",
                "message": "These inventory items have errors.",
                "count": 1,
                "data": [
                    {
                        "type": "attribute",
                        "count": 1,
                        "data": [
                            {
                                "name": "032524",
                                "status": "AVAILABLE",
                                "weight": 0,
                                "businessId": 1,
                                "locationId": 2,
                                "attributes": [
                                    ...
                                ],
                                "details": {
                                    ...
                                }
                            }
                        ]
                    }
                ]
            },
            {
                "type": "yard",
                "message": "These yards are not connected to a location.",
                "count": 1,
                "data": [
                    "2"
                ]
            }
        ]
    }
}
```

**Error: part of an load**
*TODO*
- matching bundleid and yardid is currently part of a load and cannot be updated

**Error: part of an order**
*TODO*
- matching bundleid and yardid is currently part of an order and cannot be updated
