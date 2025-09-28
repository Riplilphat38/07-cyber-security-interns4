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

4.testint the rule by attempting to connect to that port locally
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

6. Removing the test block rule to restore original state
   i removed the rule using:
   `sudo ufw delete deny 22`
