# CML-Breakout-SecureCRT-Session
performs API calls to CML and populates a secure-crt sessions for you to use with the breakout tool

Assumptions:
- secure-crt session database is in the default location. 
- using windows OS
- "populate all nodes" must be turned on in the breakout configuration. 
- This creates sessions using ipv4 loopback. 

Tested on: 
- CML: 2.2.2+build52
- breakout-windows-x86_amd64.exe 0.2.1-build-v2.2.2-52
- secureCRT 9.0.2

Variables to edit:
on main.py edit server, username, password, and lab number. 

This python app will create a new folder and all the telnet sessions for the lab. 
![alt text](https://github.com/M35a2/CML-Breakout-SecureCRT-Session/blob/main/Capture.PNG?raw=true)

