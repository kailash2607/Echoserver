# Echoserver
Echo server and client using python socket

# AIM:

To develop a simple webserver to serve html programming pages.

## DESIGN STEPS:

### Step 1:

Design of echo server and client using python socket

### Step 2:

Implementation using Python code

### Step 3:

Testing the server and client 

## PROGRAM:
# Server code:
```
import socket


HOST = "127.0.0.1"  # Standard loopback interface address (localhost)
PORT = 65432  # Port to listen on (non-privileged ports are > 1023)


with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.bind((HOST, PORT))
    s.listen()
    conn, addr = s.accept()
    with conn:
        print(f"Connected by {addr}")
        while True:
            data = conn.recv(1024)
            if not data:
                break
            conn.sendall(data)
```

# Client Code:
```
import socket


HOST = "127.0.0.1"  # The server's hostname or IP address
PORT = 65432  # The port used by the server


with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    s.sendall(b"kailash prabhu,24013672")
    data = s.recv(1024)


print(f"Received {data!r}")
```
## OUTPUT:
![Screenshot 2025-03-06 114137](https://github.com/user-attachments/assets/8ff1c26f-d7af-4c63-844a-bad3d419eb80)

![Screenshot 2025-03-06 114246](https://github.com/user-attachments/assets/033dfb60-cc1c-4256-82bf-78f31a58b602)


## RESULT:
The program is executed successfully
