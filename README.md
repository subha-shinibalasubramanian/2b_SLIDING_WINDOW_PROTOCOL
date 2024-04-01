# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
**NAME : SUBHASHINI.B**
**REGISTER NUMBER : 212223040211**
## AIM
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM

## CLIENT:

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

## SERVER:

```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True: 
 print(s.recv(1024).decode())
 s.send("acknowledgement recived from the server".encode())
```

## OUPUT

## CLIENT 
![Screenshot 2024-04-01 143647](https://github.com/NaliniG007/2b_SLIDING_WINDOW_PROTOCOL/assets/164154478/2d0a7232-9e25-4c09-972e-81bf3e4bc202)

## SERVER
![Screenshot 2024-04-01 143708](https://github.com/NaliniG007/2b_SLIDING_WINDOW_PROTOCOL/assets/164154478/a0cbc11b-9828-40aa-b3dd-5300e0c200bd)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
