## TELNET - authentication
### Statement
Find the user password in this TELNET session capture.
### Solution
We received a file named `ch2.pcap`. We can open it with Wireshark:
![enter image description here](https://i.imgur.com/XtQwD4q.png)

Filter the packet capture using `telnet`:![enter image description here](https://i.imgur.com/yq81H9O.png)

Telnet is not a secure communication protocol because it does not use any security mechanism and transfers the data over network/internet in a plain-text form including the passwords so we can easily view the data of all packets:![enter image description here](https://i.imgur.com/6F9bU1k.png)

Telnet sends characters one by one so we will have to view all packets to get the username/password in normal way. But a faster way is to right-click on a line, choose `Follow` and then `TCP Stream`. This will put all data together and we will be able to see everything that happened during the session include the username/password:![enter image description here](https://i.imgur.com/sJrZMY3.png)Password:`user`

