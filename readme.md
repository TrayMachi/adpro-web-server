# Rust Web Server (Tutorial 6)

## (1) Handle-connection, check response

In this milestone i have implemented the handle_connection function which reads the request from the client and sends the response back to the client. The response is not yet a html page. But a print that said the request was received including the requester information. This handle_connection function can be brough to live because we put TCPListener in a loop. This loop will keep listening for incoming connections and will call the handle_connection function for each connection. In this milestone, we set up 127.0.0.1:7878 as the server address. This is the address that the server will listen to for incoming connections. The server is now able to receive requests from the client and send responses back to the client.

## (2) Returning HTML
![Commit 2 Screen Capture](/assets/ReturningHTML.png)

In this milestone, i'm awware that i have nothing to response in my browser. So that i add a simple html page to the response. The html page is a simple page with a title and a heading. The html page is returned as a response to the client. The client will receive the html page and will display it in the browser. The server is now able to send html pages as responses to the client. I unwrap the read_to_string function because i know that the file exists and that it can be read. If the file does not exist or cannot be read, the server will panic and stop running. This is not a problem because the server is still in development and we can fix the issue later.

## (3) Validating Request and Selectively Responding
![Commit 3 Screen Capture](/assets/ValidatingRequest.png)

In this milestone, i'm aware that if the client sends a request to the server, the server will always send a response back to the client. This is not a good practice because the server should only respond to valid requests. In this milestone, i have implemented a check to see if the request is a valid request. If the request is a valid request, the server will send a response back to the client. If the request is not a valid request, the server will send a 404 not found response back to the client in a HTML. The server is now able to selectively respond to requests from the client.
