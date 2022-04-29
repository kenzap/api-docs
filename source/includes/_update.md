
# Update

This type of query updates exiting record stored in the Kenzap Cloud. It is mandatory to provide a 40-character record ID.

## Update Parameters

```json
"query": {
    "record": {
        "type":       "update",
        "key":        key,
        "id":         id,
        "data":       data
    }
}
```

The table below demonstrates various parameters that you can use to customize your <code>find</code> query.

Parameter | Data&nbsp;Types | Example | Required
--------- | ---------- | ------- | -------
type | <code>String</code> | <code>update</code> | Yes
[key](#update-key) | <code>String</code> | <code>ecommerce-product</code> | Yes
[id](#update-id) | <code>String</code> | <code>00232c6e9024c0d8d064af7754e1c60580fe4407</code> | Yes
[data](#update-data) | <code>Object</code> | <code>{ "title": title, "price": price }</code> | Yes

### Update key

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

### Update id

Unique Kenzap Cloud record ID. It is generated when the record is first created in the Cloud. 

```json
"id": "00232c6e9024c0d8d064af7754e1c60580fe4407"
```
<aside class="notice">
You can get record ID by specifying "_id" in the fields array of the find query.
</aside>

### Update data

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

Existing fields are mapped with the provided schema and are updated with the new value.

<aside class="notice">
If the value for the specified field is not present a new key value is created instead.
</aside>

## Update Examples

### Update existing product

> Update existing product:

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
              id:     "00232c6e9024c0d8d064af7754e1c60580fe4407",
              data:   "data": {
                                "title":        "Okinawa Sushi",
                                "description":  "A set of 7 pieces, comes with free ocha.",
                                "status":       "published".
                                "price":        "25.40"
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

Updates existing E-commerce product with the following values:

* <code>Okinawa Sushi</code> for title.
* <code>A set of 7 pieces, comes with free ocha</code> for description.
* <code>published</code> for status.
* <code>25.40</code> for price.
