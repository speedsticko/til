# Http Server Api 2.0

## A typical setup (used by CPP REST SDK).

* A listener thread sits in an infinite loop blocking on calls to HttpReceiveHttpRequest
** The HTTP_REQUEST buffer will be at least 864 bytes. If you provide some additional bytes (eg 4k) then the api will try to receive the http headers as well.
** The BODY_COPY and BODY_FLUSH flags didn't work even when I provided large buffers that would have fit the entity body. 
** For ERROR_MORE_DATA - call HttpReceiveHttpRequest with a larger buffer (will be in pBytesSent), NO_ERROR - check content length and make api call to get entity body
* create an async request context to pin the memory for the duration of the request
* use IOCP with thread pool API
* HttpReceiveHttpEntityBody to retrieve the body. You can either give it a buffer equal to content_length or make multiple calls with smaller buffers.
** Need some kind of streaming interface to piece all the chunks back together
* If an error is encountered make sure to send back an error response or the client will just wait till a timeout occurs.
