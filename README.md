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
## CLIENT:
```
import socket

HOST = '127.0.0.1'  
PORT = 65432       

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
  s.bind((HOST, PORT))
  s.listen()
  conn, addr = s.accept()
  with conn:
    print('Connected by', addr)
    while True:
      data = conn.recv(1024)
      if not data:
        break
      conn.sendall(data)
```
## SERVER:
```
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

## OUPUT
## CLIENT:
![321734735-120c605c-6dd7-4303-8715-c48d3797b290](https://github.com/HemapriyaOfficial/3a.Sockets_Creation_for_Echo_Client_and_Echo_Server/assets/147114275/422d28be-e7ac-4b25-8a2f-487bf441e34d)

## SERVER:
![321734808-ce82cb7e-a0f2-4ca8-83b9-f1d1a86a1e11](https://github.com/HemapriyaOfficial/3a.Sockets_Creation_for_Echo_Client_and_Echo_Server/assets/147114275/3ee3d650-7350-4a4b-947c-da361f9c2851)

## RESULT
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links was successfully created and executed.
