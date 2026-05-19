# 3a.CREATION FOR ECHO CLIENT AND ECHO SERVER USING TCP SOCKETS
# AIM
To write a python program for creating Echo Client and Echo Server using TCP
Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server .
4. Send and receive the message using the send function in socket.
## PROGRAM
Server
```
import socket

# Create socket
s = socket.socket()

# Bind host and port
s.bind(('localhost', 8001))

# Listen for connection
s.listen(5)

print("Waiting for client connection...")

# Accept client connection
c, addr = s.accept()

print("Connected to:", addr)

while True:
    # Receive message from client
    ClientMessage = c.recv(1024).decode()

    print("Client >", ClientMessage)

    # Send same message back to client
    c.send(ClientMessage.encode())
```
Client
```
import socket

# Create socket
s = socket.socket()

# Connect to server
s.connect(('localhost', 8001))

while True:
    # Get message from user
    msg = input("Client > ")

    # Send message to server
    s.send(msg.encode())

    # Receive echoed message
    print("Server >", s.recv(1024).decode())
```
## OUPUT
<img width="1192" height="358" alt="image" src="https://github.com/user-attachments/assets/611a9e49-3c51-4b1c-8d0e-3a181ba3360d" />

## RESULT
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.
