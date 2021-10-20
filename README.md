# CML-Breakout-SecureCRT-Session
performs API calls to CML and populates a secure-crt sessions for you to use with the breakout tool

Assumptions:
- secure-crt session database is in the default location. 
- using windows OS
- "populate all nodes" must be turned on in the breakout configuration. 
- This creates sessions using ipv4 loopback. 
- the device name in the database is the label in CML, not the CLI hostname. 

Tested on: 
- CML: 2.2.2+build52
- breakout-windows-x86_amd64.exe 0.2.1-build-v2.2.2-52
- secureCRT 9.0.2

Variables to edit:
in login.yaml edit the server name, username, password, and lab number. 

This python app will create a new folder and all the telnet sessions for the lab. 
Port numbers are listed in front of the devices name so you can quickly bounce it off the breakout tool if something doesnt seem right...

![alt text](https://github.com/M35a2/CML-Breakout-SecureCRT-Session/blob/main/Capture.PNG?raw=true)

to run the script:
- edit the variables in login.yaml (note: the lab number is the url when opening the lab on the cml server)
- run main.py file to start the program 

Example:
C:\Users\Admin\Documents\CML-Breakout-SecureCRT-Session> python .\main.py
creating: internet Node Definition: iosv
creating: csr-sdwan-3-1 Node Definition: csr1000v
creating: csr-sdwan-4-1 Node Definition: csr1000v
creating: wan-em-2 Node Definition: wan_emulator
...omitted...
Node n98 does not exist, will check all nodes from n0 to n99.
Node n99 does not exist, will check all nodes from n0 to n99.
Nodes 0-99 checked. if you need more, increase the number checked in the while loop
example: while n_id < 150:
exiting...
C:\Users\Admin\Documents\CML-Breakout-SecureCRT-Session>


easist way to update a lab after adding/deleting devices is to just delete the lab folder in secureCRT, rerun the script, and restart secureCRT

Known issues:
This has not been tested on every node type.
Some nodes only add by 1 port number in the breakout tool, some add by 2.
if you devices got out of order, check the breakout tool and see if it only added by one port after the device where it became out of order. 
if so, you can add that node definition to the "if" statement starting on line 71 of main.py
Likewise, if there is a node that cannot be consoled into, add it to the "elif" statement on line 47

