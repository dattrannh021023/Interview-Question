# • Get http://myinternal.webserver.local/test.html via telnet.

To retrieve the content of a web page using telnet, you can follow these steps:

1. Open a terminal or command prompt.
2. Start a telnet session to the web server on port 80 (the default HTTP port) by running the following command, replacing `myinternal.webserver.local` with the actual hostname or IP address of the web server:

```bash
telnet myinternal.webserver.local 80

```

1. Once connected, type the following HTTP request to request the `test.html` page:

```
GET /test.html HTTP/1.1
Host: myinternal.webserver.local

```

1. Press Enter twice to send the request.
2. You should receive the HTTP response from the web server, which will include the content of the `test.html` page if it exists.

Note that telnet is not an ideal tool for interacting with web servers, especially for handling complex web pages or secure connections (HTTPS). It's primarily used for basic testing and debugging. For everyday web browsing, a web browser is the recommended tool.