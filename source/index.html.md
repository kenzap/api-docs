---
title: Kenzap Cloud API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - javascript

toc_footers:
  - <a href="https://dashboard.kenzap.cloud/access/">Get your Cloud API key here</a>

includes:
  - authentication
  - queries
  - create
  - find
  - update
  - delete
  - errors

search: true

code_clipboard: true

meta:
  - name: description
    content: Documentation for the Kenzap Cloud API
---

# Introduction

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
          products: {
              type:       "find",
              key:        "ecommerce-product",
              fields:     ["_id", "img", "status", "price", "title"],
              limit:      25
          }
      }
  })
})
.then(response => response.json())
.then(response => {

  console.log(response)

})
```

Welcome to Kenzap Cloud API. You can use this API to access and manage the data of your installed Extensions in the **Kenzap Cloud Space**.

Extensions are building blocks of Kenzap Cloud allowing you to create progressive web applications for businesses of all sizes. All extensions are **open-sourced**. You can explore some extension examples on [Github](https://github.com/topics/kenzap-cloud).

The purpose of Kenzap API is to:

* **speed up** the development time of complex applications
* bring **highly performant** user experience
* ensure **consistency** in the ecosystem of Cloud Extensions 

The API examples are provided in JavaScript language. The example query on the right side demonstrates how to return 25 records of products stored in the Cloud Space of the E-commerce extension.

<aside class="notice">
You must replace <code>your_api_key</code> with your API key.
</aside>