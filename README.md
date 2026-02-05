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
server.py
```python
import socket

HOST = '127.0.0.1'
PORT = 65432

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.bind((HOST, PORT))
    s.listen()
    conn, addr = s.accept()
    with conn:
        print(f"Server is listening on {HOST}:{PORT}")
        print('Connected by', addr)
        while True:
            data = conn.recv(1024)
            if not data:
                break
            conn.sendall(data)

```
client.py
```python
import socket

HOST = '127.0.0.1'
PORT = 65432

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    while True:
        message = input("Enter message to send to server: ")
        s.sendall(message.encode())
        data = s.recv(1024)
        print('Received', repr(data.decode()))

```

## OUTPUT

<img width="1064" height="153" alt="image" src="https://github.com/user-attachments/assets/60318e98-ebc7-4ed7-bb99-caa11bf73e51" />

<img width="1064" height="167" alt="image" src="https://github.com/user-attachments/assets/ca92c727-2b10-4c43-ab47-19d61d3dcea0" />


## RESULT
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.
