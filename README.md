# Ex No:2a  Stop and Wait Protocol
## NAME : KAAMESH M
## REGISTER NUMBER : 212223040080
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
### CLIENT
```py
import socket
s=socket.socket()
s.bind(('localhost', 8000))
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
### SERVER
```py
import socket
s=socket.socket()
s.connect(('localhost', 8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())

```
## OUTPUT
### CLIENT OUTPUT
![CN 2a c](https://github.com/Kaameshm25/2a_Stop_and_Wait_Protocol/assets/144870650/af450485-f21d-4db8-94c8-304e3c8d54c1)

### SERVER OUTPUT
![CN 2a S](https://github.com/Kaameshm25/2a_Stop_and_Wait_Protocol/assets/144870650/db5e53ab-59ee-42cb-86d3-befd29c7d824)


## RESULT

Thus,python program to perform stop and wait protocol was successfully executed.
