# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
### NAME: Shashin prasad S
### REG.NO:212222230144
## AIM
To write a python program for Implementation of sliding Window Protocol.
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
### Server
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
size=int(input("Enter number of frames to send : "))
l=list(range(size))
s=int(input("Enter Window Size : "))
st=0
i=0
while True:
 while(i<len(l)):
 st+=s
 c.send(str(l[i:st]).encode())
 ack=c.recv(1024).decode()
 if ack:
 print(ack)
 i+=s
```
### Client
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True: 
 print(s.recv(1024).decode())
 s.send("acknowledgement recived from the server".encode())

```
<br></br>
<br></br>
<br></br>
<br></br>

## OUPUT
### Server
![Screenshot 2024-09-10 085639](https://github.com/user-attachments/assets/c54b96bc-a64b-48a9-a8ee-b608bd6d9d6d)

### Client
![Screenshot 2024-09-10 085613](https://github.com/user-attachments/assets/ddebb5c2-10a7-4f4a-b047-bd76d044afb3)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
