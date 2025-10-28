# 3b.CREATION FOR CHAT USING TCP SOCKETS
## AIM
To write a python program for creating Chat using TCP Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server
4. Send and receive the message using the send function in socket.
## PROGRAM
## CLIENT
```
import socket
s = socket.socket()
s.connect(('localhost', 8000))

while True:
    msg = input("Client > ")
    s.send(msg.encode())
    print("Server >", s.recv(1024).decode())
```
## SERVER
```
import socket
s = socket.socket()
s.bind(('localhost', 8000))
s.listen(5)
print("Server waiting for connection...")
c, addr = s.accept()
print("Connected with", addr)

while True:
    client_msg = c.recv(1024).decode()
    print("Client >", client_msg)
    msg = input("Server > ")
    c.send(msg.encode())
```
## OUPUT
<img width="1920" height="1200" alt="image" src="https://github.com/user-attachments/assets/47c98781-1513-4e0b-a43a-eba59517931f" />

## RESULT
Thus, the python program for creating Chat using TCP Sockets Links was successfully 
created and executed.
