## Request

`PUT:` `https://128.136.20.77/Bobcat/LumberMarketplace.dll/RemoveBundleFromOrder`

## Header Info

`APIkey:56915_79109110105_1_88466` (that's a key for testing)

With data like (although we still need to add the detailed pricing information to this):

```json
[
    {
        "orderid": "TESTLM3",
        "bundleids": [
            { "bundleid": "10", "yardid": "1" },
            { "bundleid": "12", "yardid": "1" }
        ]
    }
]
```

## Examples of responses you could get (not based on the data above):

-   `Good`
-   `This user is not set up for access.`
-   `Order ID: 1234 does not exist.`
-   `Error processing information.`
