#### TCP connection.
![Docker](/images/TCP_estabilish.png)
- First handshake: Client set SYN as 1. Generate a random sequence J. Send to server, Client enter SYN_SENT state.
- Second handshake: Server mark SYN and ACK to 1, ack = j + 1. Send a seq = K. Server enter SYN_RCVD state.
- Third handshake: Client check if ack = J + . ACK is 1 or not. ACK = K + 1. Client enter estabilished, after server receive ACK, it enters to estabilkished state.

![Docker](/images/TCP_release.png)
- Client send FIN. Client enter FIN_WAIT_1 state. Server receive FIN, send ACK to client. 
- Server goes to CLOSE_WAIT. for this state the client will not send to server more. Client enter FIN_WAIT_2
- Server finishs all send, and send FIN, then server enter LAST_ACK. 
- Client receive this, enter TIME_WAIT. Wait for 2 MAX Data time. ACK to server. Then server close the communication. 
 
 #### How to guarantee the realiability 
- Checksum
- Reorder
- Drop duplicate data
- Acknoledge stategy
- resend when Timeout 
- Congestion control

#### DDos attack 
- Client only send SYN to server but not ACK in stage 3. The server will wait there and take resources. 

#### GET AND PUSH
- REST. GET is idepomtent. Everytime you get same result. POST will change resource.
- GET will attach parameters on URL(HTTP Header). POST will add information in HTTP Body. 
- POST is more safe. 
- GET parameter is limited by URL length. But post is no limitation.

#### TCP congestion control 
![Docker](/images/TCP_congestion.png)
- Slow start. Send small number of packets first to detect the congestion of networking. Enponent increasing.
- Linear increase. When outlimit the window size, it will decrease half and then increase linearly.
- Repeat acknowledge when see invalid message from receive side. 
- Quick recovery. When sender receive more than three repeat acknowledge Decease the window size.(Half)

#### Access webpage from URL.
- DNS check to get the ip address.
- TCP handshake, send HTTP request.
- Server receive it and send ti back to browser.
- Browser see the result. Javascript, css.

* There could be something like CDN in system.
* Load balance 

#### HTTP 1.0 vs 1.1
![HTTP](/images/HTTP2.0.png)
- HTTP 1.1 has a requried host header. 
- HTTP 1.1 allow persistent connections
- HTTP 2.0 supports Multiplexing(多路复用), header compression, priority and packet streaming management. (Not need to multiple TCP connection)
| -> this is relevant to CDN. Pipe lines