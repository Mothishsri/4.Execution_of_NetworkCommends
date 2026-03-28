# 4.Execution_of_NetworkCommands
## AIM :Use of Network commands in Real Time environment
## Software : Command Prompt And Network Protocol Analyzer
## Procedure: To do this EXPERIMENT- follows these steps:
<BR>
In this EXPERIMENT- students have to understand basic networking commands e.g cpdump, netstat, ifconfig, nslookup ,traceroute and also Capture ping and traceroute PDUs using a network protocol analyzer 
<BR>
All commands related to Network configuration which includes how to switch to privilege mode
<BR>
and normal mode and how to configure router interface and how to save this configuration to
<BR>
flash memory or permanent memory.
<BR>
This commands includes
<BR>
• Configuring the Router commands
<BR>
• General Commands to configure network
<BR>
• Privileged Mode commands of a router 
<BR>
• Router Processes & Statistics
<BR>
• IP Commands
<BR>
• Other IP Commands e.g. show ip route etc.
<BR>


## Program
```
Server.py
import socket
from pythonping import ping
s = socket.socket()
# Bind to localhost and port
s.bind(('localhost', 8000))
# Listen for connections
s.listen(5)
print("Ping Server started... Waiting for connection")
# Accept connection
c, addr = s.accept()
print("Connected to:", addr)
while True:
    hostname = c.recv(1024).decode()
    if not hostname:
        break
    try:
        result = ping(hostname, count=4, verbose=False)
        c.send(str(result).encode())
    except:
        c.send("Host Not Found".encode())
c.close()

Client.py
import socket
# Create socket
s = socket.socket()
# Connect to server
s.connect(('localhost', 8000))
while True:
    website = input("Enter the website you want to ping: ")
    if website.lower() == "exit":
        break
    s.send(website.encode())
    result = s.recv(1024).decode()
    print("\nPing Result:\n", result)
s.close()

Traceroute.py
import os
print("Running Traceroute...\n")
os.system("C:\\Windows\\System32\\tracert.exe google.com")
```
## Output
1)ping
<img width="844" height="353" alt="image" src="https://github.com/user-attachments/assets/a96d87a3-d7d1-43dd-a57f-1530a4329e87" />
2)Tracet
<img width="1046" height="561" alt="image" src="https://github.com/user-attachments/assets/90fa26d0-5c94-4569-9066-b589e0e616e4" />
3)ipconfig
<img width="984" height="719" alt="image" src="https://github.com/user-attachments/assets/e9ac06a9-abc7-418b-8d4a-0c15775f5e2a" />
4)netstat
<img width="886" height="909" alt="image" src="https://github.com/user-attachments/assets/ba9cf26f-4917-44b1-b8bb-f12a887e359e" />
6)getmac
<img width="956" height="171" alt="image" src="https://github.com/user-attachments/assets/6a1a809e-3d24-4dbb-bdc3-8334c88be6ae" />
7)nbtstat
<img width="1105" height="600" alt="image" src="https://github.com/user-attachments/assets/86242f89-6681-4148-a4e8-c9ec593ebbd8" />
8)arp
<img width="958" height="789" alt="image" src="https://github.com/user-attachments/assets/a2eea7cf-696f-4e44-aa82-4c6bd954db3b" />
9)systeminfo
<img width="705" height="964" alt="image" src="https://github.com/user-attachments/assets/69beb668-8ecf-4e1d-b9ea-13d1747891f0" />


## Result
Thus Execution of Network commands Performed 
