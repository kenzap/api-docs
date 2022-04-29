
# Query Structure

By default all queries are sent as JSON paylod in the POST request body.

### HTTP Request

`POST https://api-v1.kenzap.cloud/`

### JSON Payload

```json
"query": {
    "records": {
        "type":       query_type
    }
}
```

<code>
query: {
    records: {
        type:       query_type
    }
}
</code>

### Query Types

Type | Description
------ | -----------
[find](#find) | Find for one or multiple records.
create | Insert new record to the Cloud Space.
update | Find record by provided _id and update it.
delete | Find record by provided _id and delete it.
set | Find record by provided reference key and update it.
get | Find record by provided reference key.
webhook | Make API call after query is processed.
authenticate | Authenticate user with the help of [kenzap_user_token](#user-token-authentication).
locale | Retrieve translation data.
api-key | Retrieve available API keys.
