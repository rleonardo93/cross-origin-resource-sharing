# Cross-Origin Resource Sharing(CORS)

Cross-Origin Resource Sharing (CORS) is an HTTP-header based mechanism that allows a server to indicate any other origins(domain, scheme, or port) than its own from which a browser should permit loading of resources. CORS also relies on a mechanism by which browsers make a "preflight" request to the server hosting the cross-origin resource, in order to check that the server will permiti the actual request. In that preflight, the browser sends headers that indicate the HTTP method and headers that will be used in the actual request.

An example of a cross-origin request: the front-end JavaScript code served from ```https://domain-a.com``` uses XMLHttpRequest to make a request for ```https://domain-b.com/data.json```.

For security reasons, browsers restrict cross-origin HTTP request initiated from scripts. For example, XMLHttpRequest and the Fetch API follow the same-origin policy. This means that a web application was loaded from unless the response from the other origins includes the rights CORS headers.

![alt text](https://mdn.mozillademos.org/files/14295/CORS_principle.png)

The CORS mechanism supports secure cross-origin requests and data transfers between browsers and servers. Modern browsers use CORS in APIs such as XMLHttpRequest or Fetch to mitigate the risks of cross-origin HTTP requests.

## Functional overview
The Cross-Origin Resource Sharing standard works by adding new HTTP headers that let servers describe which origins are permitted to read that information from a web browser. Additionally, for HTTP request methods that can cause side-effects on server data(in particular, HTTP methods other than ```GET```, or ```POST``` with certain MIME types), the specification mandates that browsers "preflight" the request, soliciting supported methods from the server, with the HTTP ```OPTIONS``` request method, and then upon "approval" from server, sending the actual request.
Servers can also inform clients whether "credentials"(such as Cookies and HTTP Authentication) should be sent with requests.
