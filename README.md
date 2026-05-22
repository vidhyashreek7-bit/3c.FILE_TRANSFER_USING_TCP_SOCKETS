# 3c.CREATION FOR FILE TRANSFER USING TCP SOCKETS
## AIM
To write a python program for creating File Transfer using TCP Sockets Links
## ALGORITHM:
1. Import the necessary python modules.
2. Create a socket connection using socket module.
3. Send the message to write into the file to the client file.
4. Open the file and then send it to the client in byte format.
5. In the client side receive the file from server and then write the content into it.
## PROGRAM
## Developed By: VIDHYA SHREE K
## Register No: 212225230296
### Client:
```
import socket
s = socket.socket()
host = socket.gethostname()
port = 60000
s.connect((host, port))
s.send("Hello Server".encode())
file = open("received_file.txt", "wb")
print("Receiving file...")
while True:
    data = s.recv(1024)
    if not data:
        break
    file.write(data)
print("File received successfully")
file.close()
s.close()

```
### Server:
```
import socket
s = socket.socket()
host = socket.gethostname()
port = 60000
s.bind((host, port))
s.listen(1)
print("Server listening...")
c, addr = s.accept()
print("Connected with", addr)
msg = c.recv(1024).decode()
print("Client says:", msg)
filename = "C:/Users/vidhya shree/Desktop/New folder/sample.txt"
file = open(filename, "rb")
data = file.read(1024)
while data:
    c.send(data)
    data = file.read(1024)
print("File sent successfully")
file.close()
c.close()
s.close()

```
## OUPUT
<img width="1920" height="1200" alt="image" src="https://github.com/user-attachments/assets/6924e7cb-03ba-484e-97ee-d82341dad81a" />
<img width="1920" height="1200" alt="image" src="https://github.com/user-attachments/assets/7f6c386e-6f95-48fb-8419-79366db17d64" />
<img width="1920" height="1200" alt="image" src="https://github.com/user-attachments/assets/b63c957d-7d1e-410b-a1c2-80862de991ad" />




## RESULT
Thus, the python program for creating File Transfer using TCP Sockets Links was 
successfully created and executed.
