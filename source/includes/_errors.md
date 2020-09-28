# Errors

The Kindmetrics API uses the following error codes:


Error Code | Meaning
---------- | -------
400 | Bad Request -- Your request is invalid.
401 | Unauthorized -- Your API key is wrong.
403 | Forbidden -- You have no permission for that request
404 | Not Found -- The specified domain could not be found.
405 | Method Not Allowed -- You tried to access a domain with an invalid method.
406 | Not Acceptable -- You requested a format that isn't json.
429 | Too Many Requests
500 | Internal Server Error -- We had a problem with our server. Try again later.
503 | Service Unavailable -- We're temporarily offline for maintenance. Please try again later.
