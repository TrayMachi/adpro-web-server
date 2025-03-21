# Rust Web Server (Tutorial 6)

## (1) Handle-connection, check response

In this milestone i have implemented the handle_connection function which reads the request from the client and sends the response back to the client. The response is not yet a html page. But a print that said the request was received including the requester information. This handle_connection function can be brough to live because we put TCPListener in a loop. This loop will keep listening for incoming connections and will call the handle_connection function for each connection. In this milestone, we set up 127.0.0.1:7878 as the server address. This is the address that the server will listen to for incoming connections. The server is now able to receive requests from the client and send responses back to the client.
