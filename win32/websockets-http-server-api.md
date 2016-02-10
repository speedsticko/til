# WebSockets in HTTP Server API 2.0

Server-side webSockets is only supported in Http.Sys on Windows 8+. 
This was made possible throw the new flag HTTP_SEND_RESPONSE_FLAG_OPAQUE that is used with HttpSendHttpResponse () to implement the WebSockets handshake.

The tricky bit is getting the flags right. Here's the sequence of steps:

* Read a request for a WebSockets upgrade
* Build the WebSockets handshake response and send it back to the client with HttpSendHttpResponse:
** status code must be 101
** must set the correct http headers:
** set the flags: HTTP_SEND_RESPONSE_FLAG_OPAQUE and HTTP_SEND_RESPONSE_FLAG_MORE_DATA.
** provide a buffer for the next request

Now, you can continue with your WebSockets session by using: HttpSendResponseEntityBody and HttpReceiveRequestEntityBody. 
Make sure the flag for the receive call is 0 unless you're ready to end the session.
