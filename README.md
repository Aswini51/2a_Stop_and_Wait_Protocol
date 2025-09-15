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
# CLIENT:
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
# SERVER:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Received".encode())
```
## OUTPUT
# CLIENT:
<img width="1268" height="243" alt="Screenshot 2025-09-15 140541" src="https://github.com/user-attachments/assets/853b8548-448a-41e8-9622-45d6b59826b6" />

# SERVER:
<img width="1270" height="222" alt="Screenshot 2025-09-15 140622" src="https://github.com/user-attachments/assets/0e8a1121-9b10-4020-874d-0056a6137f80" />

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
