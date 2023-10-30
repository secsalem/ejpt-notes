TL:DR 
target = 192.168.2.3
- nmap 192.168.2.3 -p- -v  - get ports
- nmap 192.168.2.3  -p 177,22,2456 -v -A - service on ports
- nmap 192.168.2.3 -p 1-250 -sUV get UDP ports
- nmap 192.168.2.3 -p  134,177,234 -sUV -A - services on ports  
- nmap 192.168.2.3 -p  134 -sUV --script=discovery - if port didn't give details
------------------------------
first 
ifconfig 
we have our target for example 
IP: 192.168.2.3
nmap scan to check open ports 
- nmap -p- -v 192.168.2.3
we will get the open ports 
we will scan the open ports which services it's running 

- nmap -p 177,22,2456 192.168.2.3 -v -A

this will give us more infomration it may show us a tcp only ports and service we will do UDP scan , since it takes more time we will narrow it to the top 250 ports 

- nmap 192.168.2.3 -p 1-250 -sUV

we will get UDP ports results 

we will get service running on them 


- nmap 192.168.2.3 -p  134,177,234 -sUV -A
or 
- nmap 192.168.2.3 -p  134,177,234 -sUV 

we will get the service running on UDP ports 

in some cases some ports will not show us the services running on them we can try a nmap script discovery 

- 
nmap 192.168.2.3 -p  134 -sUV --script=discovery



