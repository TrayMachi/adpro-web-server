# Rust Web Server (Tutorial 6)

## (1) Handle-connection, check response

In this milestone i have implemented the handle_connection function which reads the request from the client and sends the response back to the client. The response is not yet a html page. But a print that said the request was received including the requester information. This handle_connection function can be brough to live because we put TCPListener in a loop. This loop will keep listening for incoming connections and will call the handle_connection function for each connection. In this milestone, we set up 127.0.0.1:7878 as the server address. This is the address that the server will listen to for incoming connections. The server is now able to receive requests from the client and send responses back to the client.

## (2) Returning HTML
![Commit 2 Screen Capture](/assets/ReturningHTML.png)

In this milestone, i'm awware that i have nothing to response in my browser. So that i add a simple html page to the response. The html page is a simple page with a title and a heading. The html page is returned as a response to the client. The client will receive the html page and will display it in the browser. The server is now able to send html pages as responses to the client. I unwrap the read_to_string function because i know that the file exists and that it can be read. If the file does not exist or cannot be read, the server will panic and stop running. This is not a problem because the server is still in development and we can fix the issue later.

## (3) Validating Request and Selectively Responding
![Commit 3 Screen Capture](/assets/ValidatingRequest.png)

In this milestone, i'm aware that if the client sends a request to the server, the server will always send a response back to the client. This is not a good practice because the server should only respond to valid requests. In this milestone, i have implemented a check to see if the request is a valid request. If the request is a valid request, the server will send a response back to the client. If the request is not a valid request, the server will send a 404 not found response back to the client in a HTML. The server is now able to selectively respond to requests from the client.

## (4) Simulation of slow request.

We aware that even though our server is running, but it's running on single thread. So that if we send multiple request to the server, the server will only be able to handle one request at a time. This is not a good practice because the server should be able to handle multiple requests at the same time. In this milestone, i have implemented a sleep function to simulate a slow request. The sleep function will make the server sleep for 10 seconds before sending a response back to the client. This will make the server slow and will not be able to handle multiple requests at the same time. The server is now able to simulate a slow request.

## (5) Multithreaded server using Threadpool

In this milestone, i have implemented a thread pool to make the server multithreaded. The thread pool will create a number of threads and will keep them alive. When a request is received, the thread pool will assign a thread to handle the request. The thread will call the handle_connection function to read the request from the client and send the response back to the client. The thread pool will keep the threads alive and will reuse them to handle multiple requests. The server is now able to handle multiple requests at the same time. We put 4 worker threads in the thread pool. This means that the server can handle 4 requests at the same time. If the server receives more than 4 requests, the requests will be queued and will be handled when a thread is available.