## FTP - authentication
### Statement
An authenticated file exchange achieved through FTP. Recover the password used by the user.
### Solution
We received a file named `ch1.pcap`. We can open it with Wireshark:
![enter image description here](https://i.imgur.com/x70hrpB.png)FTP has been officially assigned ports 20 and 21. If specifically using an "active" connection setting, this means that while a client computer makes the connection request and sends the commands first on port 21, known as the "control port", a connection to the server on port 20, the "data port", is also automatically opened to transfer the file data.

So all we need to do is filter the packet capture using `tcp.port==20 || tcp.port==21`:
![enter image description here](https://i.imgur.com/L4CmQ5A.png)

Look at line 11 and we will find the password:
![enter image description here](https://i.imgur.com/unJhIAa.png)
Password: `cdts3500`
