# The Same Origin Policy and CORS

The Same Origin policy is a browser security sandbox mechanism that prevents client-side scripts from getting at data from outside of the  "same origin". Note that this policy does not apply to things like the script tag which can load files from anywhere (like a CDN). What we're talking about are things like using jQuery to make a XmlHttpRequest to another site.

There are several ways around this policy:
- Cross-Origin Resource Sharing
- Cross-Document communication with iframes and postMessage()
- document.domain
- JSONP
- WebSockets
- window.name
- HTTP proxy
