# 2a_Stop_and_Wait_Protocol
## Name : Vinuthaa NN
## Reg no: 212224040362
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
CLIENT CODE:
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
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
SERVER CODE:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())
```
## OUTPUT

<img width="1064" height="494" alt="image" src="https://github.com/user-attachments/assets/f7335183-e1af-4b92-98ee-0e71a684b467" />
<img width="1044" height="495" alt="image" src="https://github.com/user-attachments/assets/705d4aa2-16cf-48b1-bd69-3360b33a115f" />

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
