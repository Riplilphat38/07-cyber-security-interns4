# 07-cyber-security-interns4
## Setup and Use a Firewall on Linux
1- Installation
--
I installed UFW using:
> sudo apt install ufw -y

![image alt](https://github.com/Riplilphat38/07-cyber-security-interns4/blob/bb8a2ffe24c35591020e4247930c3cc56a3b9881/Screenshot%20From%202025-09-26%2021-22-55.png)

2-The current firewall rules
--
I checked the firewall rules usin:
`sudo ufw status verbose`

![image alt](https://github.com/Riplilphat38/07-cyber-security-interns4/blob/3a61c56a3c7bf76df558ce30fcf94544416d17ea/72d37d94-52e1-45cc-85b2-70da1c8a67ab.jpeg)

3.Adding a rule to block inbound traffic on a specific port (23 for telnet)
--
I added the rule using:
`sudo ufw deny 23`

4.testing the rule by attempting to connect to that port locally
--
I opened a new terminal an runned:
`telnet localhost 23`
The output was "Connection failed: Connection refused"
 &&
"Telnet: Unable to connect to remote host: Connection refused"

5.Addind rule to allow SSh
--
using:
`sudo ufw allow 22`

6.Removing the test block rule to restore original state
--
   I removed the rule using:
   `sudo ufw delete deny 22`
![image alt](https://github.com/Riplilphat38/07-cyber-security-interns4/blob/177e423ba89a6d1d02191ed034632f8fe3fdbf55/708942ba-fa4d-45f6-8cb6-3c04a431009c.jpeg)

7.Documentation of commands used
 --
 
1. Check current rules
`sudo ufw status verbose`
2. Block Telnet
sudo ufw deny 23
3. Test the block
`telnet localhost 23`
4. Allow SSH
`sudo ufw allow 22`
5. Enable firewall
`sudo ufw enable`
6. Remove Telnet block when done
`sudo ufw delete deny 23`
7. Verify final state
`sudo ufw status`

8. Summarize how the firewall filters traffic
   --
Basic Filtering Mechanisms
--

a. Packet Filtering (Stateless)
--
* Examines IP headers (source/ destination address, protocol, ports)
* Applies static predefined rules
* Fast but less secure
* Does not track connection state
  
b. Stateful Firewall
--
* Maintains a state table of connections
* Remembers context of TCP/UDP
sessions
* Smarter - allows return traffic without explicit rules
* Blocks unsolicited traffic

c.Application Filtering (Proxy)
--
* Inspects packet content (OSI Layer 7)
* Understands application protocols
(HTTP, FTP, DNS)
* Can block specific content types
* Slower but more secure
