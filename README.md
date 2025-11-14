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
Client:
```
import socket

client = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
client.connect(('localhost', 8000))

while True:
    msg = input("Client > ")

    if msg.strip() == "":
        break

    client.send(msg.encode())

    data = client.recv(1024).decode()
    print("Server >", data)

client.close()

```

server:
```
import socket

server = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
server.bind(('localhost', 8000))
server.listen(1)

print("Server is ready...\n")

conn, addr = server.accept()
print(f"Client connected from {addr}\n")

while True:
    data = conn.recv(1024).decode()
    if not data:
        break

    print(f"Client > {data}")
    print(f"Server > {data}")

    conn.send(data.encode())

conn.close()
server.close()

```


## OUPUT
<img width="1917" height="1188" alt="image" src="https://github.com/user-attachments/assets/61a0e07e-1ed1-4a40-8866-20d4de74b3be" />

## RESULT
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.
