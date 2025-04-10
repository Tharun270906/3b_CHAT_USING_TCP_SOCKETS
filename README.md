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

client 
```
import socket 
s=socket.socket() 
s.bind(('localhost',7000)) 
s.listen(5) 
c,addr=s.accept() 
address={"6A:08:AA:C2":"192.168.1.100","8A:BC:E3:FA":"192.168.1.99"}; 
while True: 
            ip=c.recv(1024).decode() 
            try: 
                c.send(address[ip].encode()) 
            except KeyError: 
                c.send("Not Found".encode())
```

Server
```

import socket 
s=socket.socket() 
s.connect(('localhost',7000)) 
while True: 
    ip=input("Enter MAC Address : ") 
    s.send(ip.encode()) 
    print("Logical Address",s.recv(1024).decode())
```
## OUPUT
![cn ex3B](https://github.com/user-attachments/assets/784e0ba4-3e7c-49f5-b50f-9e82b08843b5)

## RESULT
Thus, the python program for creating Chat using TCP Sockets Links was successfully 
created and executed.
