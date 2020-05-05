# Errors

<aside class="notice">
The PeerPal API uses the following error codes:
</aside>

| Error Code | Meaning                                                                                   |
| ---------- | ----------------------------------------------------------------------------------------- |
| 400        | Bad Request -- Your request is invalid.                                                   |
| 401        | Unauthorized -- Your API key is wrong.                                                    |
| 403        | Forbidden -- The route requested is hidden for administrators only.                       |
| 404        | Not Found -- The specified route could not be found.                                      |
| 405        | Method Not Allowed -- You tried to access a route with an invalid method.                 |
| 406        | Not Acceptable -- You requested a format that isn't JSON.                                 |
| 410        | Deleted -- The item requested has been removed from our servers.                          |
| 429        | Too Many Requests -- You're requesting too many times! Slow down!                         |
| 500        | Internal Server Error -- We had a problem with our server. Try again later.               |
| 503        | Service Unavailable -- We're temporarily offline for maintenance. Please try again later. |
