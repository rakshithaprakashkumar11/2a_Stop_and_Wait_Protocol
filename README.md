### 2a_Stop_and_Wait_Protocol
### AIM: 
To write a python program to perform stop and wait protocol
### ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
### PROGRAM:
## Client Output:
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
## Server Output:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("Acknowledgement Recived".encode())
```
### OUTPUT:
## Client output:
![Screenshot 2024-03-01 140911](https://github.com/rakshithaprakashkumar11/2a_Stop_and_Wait_Protocol/assets/150994181/48c84c54-b352-4e0e-ad9b-705f2f9048dc)
## Server Output:
![Screenshot 2024-03-01 141544](https://github.com/rakshithaprakashkumar11/2a_Stop_and_Wait_Protocol/assets/150994181/4981d763-0840-45aa-91cc-5c0af8f23a22)

### RESULT:
Thus, python program to perform stop and wait protocol was successfully executed.
