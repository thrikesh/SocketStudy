# Ex.No:1a  			Study of Socket Programming
### NAME : THRIKESWAR P
### REG.NO:212222230162
## Aim: 
To perform a study on Socket Programming
## Introduction:
Socket programming is a crucial aspect of network communication, allowing for data exchange between computers over a network. It forms the backbone of various networked applications, enabling communication between clients and servers. This study explores the fundamental concepts of socket programming, its use cases, and provides a practical example to demonstrate its implementation.
## Understanding Socket Programming:
Socket programming involves the use of sockets, which serve as endpoints for communication. A socket is identified by an IP address and a port number, and it facilitates data transfer between a client and a server. The two main types of sockets are Stream Sockets, which provide a reliable, connection-oriented communication, and Datagram Sockets, which are connectionless and suitable for scenarios where reliability is less critical.
## Key Concepts in Socket Programming:
1.Sockets

•	A socket is a software representation of a communication endpoint in a network.</br>
•	It is identified by an IP address and a port number.</br>
•	Sockets can be classified into two main types: Stream Sockets and Datagram Sockets.</br>
•	Stream Sockets provide a reliable, connection-oriented communication, while Datagram Sockets are connectionless and operate in a best-effort mode.</br>

2.Client-Server Model

•	Socket programming typically follows the client-server model.</br>
•	The server listens for incoming connections from clients, while clients initiate connections to the server.</br>
•	Servers are passive, waiting for connection requests, and clients are active, initiating communication.</br>

3, TCP/IP Protocol:

•	Transmission Control Protocol (TCP) and Internet Protocol (IP) are the foundational protocols for socket programming.</br>
•	TCP provides reliable, connection-oriented communication, ensuring data integrity and order.</br>
•	IP facilitates the routing of data between devices in a network.</br>

4.Basic Socket Functions:

•	Socket programming involves a set of functions provided by the operating system or programming language to create, bind, listen, accept, connect, send, and receive data through sockets.</br>
•	Examples of functions include socket(), bind(), listen(), accept(), connect(), send(), and recv().</br>

## Server-Side Operations:

•	Servers create a socket using socket() and bind it to a specific IP address and port using bind().</br>
•	They then listen for incoming connections with listen() and accept connections with accept().</br>
•	Once a connection is establish </br>
•	shed, servers can send and receive data using send() and recv().</br>

## Client –Server Operations

Clients create a socket using socket() and connect to a server using connect().</br>
After establishing a connection, clients can send and receive data using send() and recv().</br>

## Use Cases of Socket Programming:

Socket programming finds applications in various domains, including web development, file transfer protocols, online gaming, and real-time communication. It is the foundation for protocols like HTTP, FTP, and SMTP, which power the internet. Socket programming enables the development of both server and client applications, facilitating the exchange of information between devices in a networked environment.

## Example Use Cases:

1.	Web servers: Web servers use socket programming to handle incoming HTTP requests from clients, serving web pages and content.</br>
2.	Chat Application: Instant messaging and chat applications use sockets to enable real-time communication between users.</br>
3.	File Transfer Protocol: Protocols like FTP (File Transfer Protocol) utilize socket programming for transferring files between a client and a server.</br>
4.	Networked Games: Online multiplayer games rely on socket programming to facilitate communication between game clients and servers.</br>
5.	RPC mechanisms: which allow processes to execute code on a remote server, often use socket programming for communication.</br>

## PROGRAM 
 ### CLIENT:
 ```
import socket
from datetime import datetime
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
print("Client Address : ",addr)
now = datetime.now()
c.send(now.strftime("%d/%m/%Y %H:%M:%S").encode())
ack=c.recv(1024).decode()
if ack:
 print(ack)
c.close()
```
### SERVER
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
print(s.getsockname())
print(s.recv(1024).decode())
s.send("acknowledgement recived from the server".encode())
```
## OUTPUT
 ### CLIENT:
![image](https://github.com/Yuvaranithulasingam/SocketStudy/assets/121418522/8a60e5ee-7095-43cb-aac3-0aa9f7197eb5)

### SERVER:
![image](https://github.com/Yuvaranithulasingam/SocketStudy/assets/121418522/7c591d08-b710-4e47-a585-cb6b052ab183)

## Result:
Thus the study of Socket Programming Completed Successfully
