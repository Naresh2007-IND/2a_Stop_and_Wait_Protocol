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
Developed by : **Naresh J**
Register Number : **212225230195**
###server
```
  import socket
  s=socket.socket()
  s.connect(('localhost',8080))
  while True: 
      print(s.recv(1024).decode())
      s.send("acknowledgement recived from the server".encode())
```
###client

 ```
  import socket
  s=socket.socket()
  s.bind(('localhost',8080))
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
## OUTPUT
<img width="1705" height="251" alt="image" src="https://github.com/user-attachments/assets/27b62f65-a6dd-4036-8482-386b2bdb4929" />

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
