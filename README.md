# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## AIM
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
Reg.no: 212223040220
Developed by: Swathi S
## Server
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
## Client 
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True: 
 print(s.recv(1024).decode())
 s.send("acknowledgement recived from the server".encode())
```
## OUPUT
## Client 
![image](https://github.com/SwathidoraiS/2b_SLIDING_WINDOW_PROTOCOL/assets/144870557/f530b626-43c3-4549-a63a-f9439afb07e2)

## Server
![image](https://github.com/SwathidoraiS/2b_SLIDING_WINDOW_PROTOCOL/assets/144870557/83150829-b393-46bd-a405-2f44662e4505)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
