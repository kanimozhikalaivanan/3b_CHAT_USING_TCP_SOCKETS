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
## server.py
```
import socket

s = socket.socket()
s.bind(('localhost', 8000))
s.listen(1)

print("Server is waiting for connection...")

c, addr = s.accept()
print("Connected to:", addr)

while True:
    msg = c.recv(1024).decode()
    print("Client >", msg)
    reply = input("Server > ")
    c.send(reply.encode())
```
## client.py
```
import socket

s = socket.socket()
s.connect(('localhost', 8000))

while True:
    msg = input("Client > ")
    s.send(msg.encode())
    print("Server >", s.recv(1024).decode())
```
## OUPUT
## server:
<img width="1540" height="1021" alt="Screenshot 2026-03-25 132759" src="https://github.com/user-attachments/assets/fc761b9b-2928-4552-adc9-78519f3f70c3" />
## client:
<img width="1576" height="978" alt="Screenshot 2026-03-25 132737" src="https://github.com/user-attachments/assets/ff1d6071-2ece-423c-82a9-a6c4e5d61094" />

## RESULT
Thus, the python program for creating Chat using TCP Sockets Links was successfully 
created and executed.
