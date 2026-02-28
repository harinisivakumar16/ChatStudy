# Ex. No:1b 			Study of Client Server Chat Applications

## Aim: 
To perform a study on Client Server Chat Applications
## Introduction:
Client-server chat applications are a category of networked software that enables real-time communication between users over a network. This study explores the key components, architecture, and considerations in the development of client-server chat applications, highlighting their significance and common implementation practices.
Client-server chat applications are software systems that enable real-time communication between users over a network. These applications follow a client-server model, where one component (the server) manages connections and facilitates communication, while the other component (the client) interacts with the server to send and receive messages. Below are the fundamental aspects and components involved in the basics of client-server chat applications:
## 1. Client-Server Model:
•	Server:
•	The server is a central component that listens for incoming connections from clients.
•	It manages the communication channels and facilitates the exchange of messages between clients.
•	It may handle user authentication, message routing, and other core functionalities.
•	Client:
•	Clients are users or devices that connect to the server to participate in the chat.
•	Each client has a unique identity, often represented by a username.
•	Clients interact with the server to send and receive messages.
## 2. Communication Protocols:
•	Communication between clients and servers often relies on established protocols. The choice of protocol influences the behavior of the chat application.
•	TCP (Transmission Control Protocol):
•	Provides reliable, connection-oriented communication.
•	Ensures the ordered and error-free exchange of messages.

•	UDP (User Datagram Protocol):
•	Connectionless and operates in a best-effort mode.
•	Faster but may result in message loss or disorder.
## 3. Socket Programming:
•	Sockets:

•	Sockets serve as communication endpoints.
•	Each client and the server has a socket for sending and receiving data.

•	Functions:
•	Socket programming involves functions for creating, binding, listening, accepting connections, and sending/receiving data through sockets.
## 4. User Authentication:
•	For security and privacy, chat applications often implement user authentication mechanisms.
•	Users are required to provide credentials (e.g., username and password) to access the chat system.
•	More advanced methods like tokens or secure protocols can enhance authentication.
5. Message Routing:
•	The server is responsible for routing messages from one client to another.
•	It ensures that messages are delivered to the intended recipients.
•	Message routing may involve maintaining a list of connected users and their associated sockets.

## Architecture:
## Client-Server Model:
```
import socket

client = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

client.connect(("localhost", 9999))

done=False

while not done:
    client.send(input("Message ").encode('utf-8'))
    msg = client.recv(1024).decode('utf-8')

    if msg == 'quit':
        done=True
    else:
        print(msg)



client.close()
```

## Server-Side Components:
```
import socket
from base64 import decode
from operator import truediv

server =socket.socket(socket.AF_INET, socket.SOCK_STREAM)
server.bind(('localhost', 9999))
server.listen()
client,addr=server.accept()

done = False

while not done:
    msg = client.recv(1024).decode('utf-8')

    if msg == 'quit':
        done = True
    else:
        print(msg)

    client.send(input("Message ").encode('utf-8'))


client.close()
server.close()
```
## Output

<img width="1032" height="278" alt="Screenshot 2026-02-28 205610" src="https://github.com/user-attachments/assets/c340eecd-e32b-4911-8932-76064b9c5e70" />


## Result:

Thus the study on Client Server Chat Applications has been performed

