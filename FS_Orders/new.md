## Request

`PUT:` `https://128.136.20.77/Bobcat/LumberMarketplace.dll/NewOrder`

## Header Info

`APIkey:56915_79109110105_1_88466` (that's a key for testing)

With data like (although we still need to add the detailed pricing information to this):

```json
[
    {
        "orderid":"TESTLM3",
        "status":"created",
        "bundleids":[{"bundleid":"10","yardid":"1"},{"bundleid":"12","yardid":"1"}]
        "shippinginformation": {
        "name":"Johns Lumber Yard",
        "businessid":"123456789",
        "address1":"123 Main St",
        "address2":"Suite A",
        "city":"Anytown",
        "state":"CA",
        "zip":"12345",
        "country":"US",
        "phone":"123-456-7890"
        },
            "pricingInformation": {
            "lumber":"100.00",
            "shipping":"10.00",
            "platform":"10.00",
            "total":"120.00"
        }
    }
]
```

## Examples of responses you could get (not based on the data above):

-   `Good`
-   `This user is not set up for access.`
-   `Order ID: 1234 already exists.`
-   `Order ID: 1234 already exists and was cancelled.`
-   `Order ID: 1234 already exists and was shipped.`
-   `Bundle ID: 1 does not exist in Yard ID: MAIN.`
-   `Bundle ID: 1 in Yard ID: MAIN is not available.`
-   `Error saving Order ID: 1234`
-   `Error processing information.`
