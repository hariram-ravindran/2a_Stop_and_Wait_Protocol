# 2a_Stop_and_Wait_Protocol
## AIM 
To write a python program to perform stop and wait protocol
## ALGORITHM
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
client
```
import socket
s=socket.socket()
s.listen(5)
s.bind(('localhost',8000))
c,addr=s.accept()
while True:
 i=input("Enter a data: ")
 c.send(i.encode())
 ack=c.recv(1024).decode()
 if ack:
   print(ack)
   continue
 else:
   c.close()
   break
```
server
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("Acknowledgement Recived".encode())
```
## OUTPUT
CLIENT
![365879883-2ce9fb72-eb3f-402a-8ef7-437c426148b9](https://github.com/user-attachments/assets/e75818be-b846-468c-a76f-2b39e46f8cae)
SERVER
![365879948-694d7265-8fbd-45ab-96c5-3783bdb19565](https://github.com/user-attachments/assets/a27a9d30-a031-4465-9f52-9cf5ec9e3abb)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
