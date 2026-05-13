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

Developed by : Abdul Rahim M
Register number : 212225040007

```python
server.py

import socket

s = socket.socket()
s.bind(('localhost', 8000))
s.listen(1)

print("Waiting for connection...")
conn, addr = s.accept()
print("Connected to", addr)

while True:
    data = conn.recv(1024).decode()
    if not data:
        break

    print("Frame received:", data)
    conn.send("ACK".encode())

conn.close()

client.py

import socket

s = socket.socket()
s.connect(('localhost', 8000))

n = int(input("Enter number of frames: "))

for i in range(n):
    msg = input("Enter frame: ")
    s.send(msg.encode())

    ack = s.recv(1024).decode()
    print("Received:", ack)

s.close()

```
## OUTPUT

<img width="602" height="192" alt="image" src="https://github.com/user-attachments/assets/9f60d8c2-dfd9-4a8e-a0ab-646ee5a50c2b" />

<img width="643" height="183" alt="image" src="https://github.com/user-attachments/assets/02d7a933-acab-45ae-9918-044dd7f3b05d" />


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
