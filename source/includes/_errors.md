# Errors

<aside class="notice">
Along with the error code status, the Kenzap Cloud API provides additional notes when the query is not successful. Most popular error reference can be found in the table below.
</aside>

The Kenzap API uses the following error codes:


Error Code | Meaning
---------- | -------
400 | Bad Request -- For example, query parameter is not specified.
401 | Unauthorized -- Your user token is wrong or expired .
403 | Forbidden -- No rights to access the resource.
404 | Not Found -- The specified kitten could not be found.
411 | Restricted --  Not enough permissions to access this data.
429 | Too Many Requests -- Too many API calls.
500 | Internal Server Error -- We had a problem with our server. Try again later.
503 | Service Unavailable -- We're temporarily offline for maintenance. Please try again later.
