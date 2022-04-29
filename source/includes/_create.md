
# Create

This type of query creates new Kenzap Cloud record and returns 40 character generated ID string.

## Create Parameters

```json
"query": {
    "record": {
        "type":       "create",
        "key":        key,
        "data":       data
    }
}
```

The table below demonstrates various parameters that you can use to customize your <code>find</code> query.

Parameter | Data&nbsp;Types | Example | Required
--------- | ---------- | ------- | -------
type | <code>String</code> | <code>create</code> | Yes
[key](#create-key) | <code>String</code> | <code>ecommerce-product</code> | Yes
[data](#create-data) | <code>Object</code> | <code>{ "title": title, "price": price }</code> | Yes

### Create key

```json
"key": "ecommerce-product"
```

This parameter specifies which extension data to query within the Cloud Space. Key names are **arbitrary**, meaning that each extension is having its own set of available keys. Think of keys as tables in the context of relational databases.

For example, E-commerce extension keys:

* <code>ecommerce-product</code>
* <code>ecommerce-settings</code>
* <code>ecommerce-order</code>

MyTicket extension keys:

* <code>myticket-settings</code>
* <code>myticket-layouts</code>                   

### Create data

```json
"data": {
          "title":        title,
          "description":  description,
          "status":       status.
          "img":          [],
          "price":        price
        }
```

Kenzap Cloud does not follow strict schema, meaning that any extension can define its own data structure and columns.

This parameter contains all payload data that you want to permanently store in the Kenzap Cloud.

## Create Examples

### Create new product

> Create new product:

```javascript
fetch("https://api-v1.kenzap.cloud/", {
  method: "post",
  headers: {
    "Accept": "application/json",
    "Content-Type": "application/json",
    "Authorization": "Bearer your_api_key"
  },
  body: JSON.stringify({
      query: {
          product: {
              type:   "create",
              key:    "ecommerce-product",
              data:   "data": {
                                "title":        "California Sushi",
                                "description":  "A set of 6 pieces, comes with free ocha.",
                                "status":       "published".
                                "price":        "24.50"
                              }
          }
      }
  })
})
.then(response => response.json())
.then(response => {

  console.log(response);

})
```

Insert new E-commerce product with the following values:

* <code>California Sushi</code> for title.
* <code>A set of 6 pieces, comes with free ocha</code> for description.
* <code>published</code> for status.
* <code>24.50</code> for price.
