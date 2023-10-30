nmap -Pn -F -sV  185.230.63.107
-O opertaing system detection 
-F faster scan 
-sV probe ports for there services 
-Pn treat all hosts as online 
-sC run default scripts 
-p- scan all ports 
-oN output nmap scan 
-h for more options 
detect ports and there services and version 

arp-scan -g 192.168.0.1 

we will get set of ports 

further enum ports with nmap 

nmap 192.168.0.1 -Pn -p 80,443,139,3456,5674 -sV -O 

we will get more details on ports 

-- 



