# CML-Breakout-SecureCRT-Session
performs API calls to CML and populates a secure-crt sessions for you to use with the breakout tool

Assumptions:
secure-crt session database is in the default location. 
using windows OS
"populate all nodes" must be turned on in the breakout configuration. 
This creates sessions using ipv4 loopback. 

Tested on: 
Remote controller version: 2.2.2+build52
Local Breakout version:
breakout-windows-x86_amd64.exe 0.2.1-build-v2.2.2-52
Build info:
  Built:      2021-06-07T08:58:44Z
  Git commit: 3f7bf91a8dc833af
  Go version: go1.15.3
  Platform:   linux/amd64
  Build host: virl-rtp-jenkins-1.cisco.com 4.18.0-193.19.1.el8_2.x86_64 x86_64
