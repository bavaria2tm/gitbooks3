# Test2

- Lets go

## 1. General

### Description

* This API provides deleted designs data by amazon.
* This API is used in the following Applications:
  * `WebApp`

### Notes

* n/a

***

## 2. API Info

### Methods / URL

```
GET: {HOST}/research/deleted-designs/{SEARCH_TERM}
```

### Parameters

```javascript
    SEARCH_TERM : STRING [1]
```

```
    [1] SEARCH_TERM is optional
```

### Query Parameters

```javascript
    sort_by         : String [1]    // Enum available here => /shared_sync/constants/shared/research/research_api/deleted-designs.constants.ts
    page            : Number    
    search_type     : String [2]    // Enum available here => /shared_sync/constants/shared/research/research_api/deleted-designs.constants.ts
    marketplace     : String [3]
    product         : String 
    from_date       : Date
    to_date         : Date
    
```

```javascript
    // Values for the parameters
    [1] "sort_by" values: "newest" / "oldest" / "bsr" / "price" / "relevant" / "random" / "review"
    [2] Values : "default" / "specific" / none ("if search_type is not avaliable then API will use 'default'")
    [3] Values : 'all_markets', 'com', 'co_uk', 'de', 'fr', 'it', 'es'
```

&#x20;

***

## 3. Response

### Success

```javascript
    HTTP code       : 200
    HTTP message    : OK
    Response type   : JSON
```

```javascript
    {
        "result" : [
            { 
                "id"              : Number,
                "asin"            : String,
                "brand"           : String,
                "title"           : String,
                "img"             : String,
                "product"         : String,
                "marketplace"     : String,
                "price"           : Number,
                "bsr"             : Number,
                "review_stars"    : Number,
                "review_count"    : Number
            },
            ...
        ]
        "returnedResults" : Number,
    }
```

### Error

* Please check `common error responses` [here](../common/error\_response.md).
* Please check `HTTP status codes` [here](../common/http\_code.md).

&#x20;

***

## 4. Examples

### Example 1: get deleted designs result

```javascript
    //Request
    GET: {HOST}/research/deleted-designs/{SEARCH TERM}
    
    //Response
    {
        "result" : [
            { 
                "id"              : 123,
                "asin"            : "BQ123456",
                "brand"           : "Test",
                "title"           : "Test",
                "img"             : "Demo Image",
                "product"         : "T-shirt",
                "marketplace"     : "en",
                "price"           : 100,
                "bsr"             : 500,
                "review_stars"    : 5,
                "review_count"    : 500
            },
            ...
        ]
        "returnedResults"   : 10,
    }
```
