---
layout: post
title:      "The Deal With WebSockets"
date:       2018-10-21 23:04:28 -0400
permalink:  es6_arrow_functions_in_depth2
---

**Introduction**

WebSockets were created to solve the issue of transferring data between client and server. Traditionally, a full HTTP request was necessary for each and every data transfer. Because a full HTTP request transfers cookies and headers as well, the amount of data being transferred for requests was often more than was necessary, which in turn unnecessarily increase latency time. 

**Setting up the Connection**

WebSockets provide a constant connection between client and server, giving both parties the capability of transferring data at any time. To initiate a WebSocket, the client sends a full HTTP request to the server, with an `Upgrade` header that tells the server to establish a WebSocket. If the server accepts the request, it sends back a response with an `Upgrade` header indicating that it was successful. At this point, the HTTP request is replaced with the WebSocket connection and the WebSocket setup is complete and ready to be used. This setup step is call the WebSocket handshake. 

**Transferring Data with WebSockets**

WebSockets transfer data through messages, each of which contains at least one frame. These frames contain the data itself, known as the payload. Each frame that is transferred is prefixed with 4-12 bytes of data that identifies the data in that particular frame. This ensures that when the frame reaches the client, it can be reconstructed. The client is notified after all the frames are received and the messages are reconstructed. Using frames for transferring data reduces the non-payload data that is transferred, greatly reducing the amount of latency. 





