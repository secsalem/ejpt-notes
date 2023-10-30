tools for port scanning 
Zenmap 
Nmap automator 
Masscan 
Rustscan 
Autorecon

some nmap commands

#### OS Detection

nmap -Pn -O 10.10.10.10

#### Nmap Scan (Quick)

nmap -sC -sV 10.10.10.10

#### Nmap Scan (Full)

nmap -sC -sV -p- 10.10.10.10

#### Nmap Scan (UDP Quick)

nmap -sU -sV 10.10.10.10

you can nmap list of ips you get from example 
nmap -iL "ips.txt"

ofc that's after getting the list of ips /24 subnet 
nmap -sn 10.10.10.0/24  
nmap -sV -p- -iL targets -oN nmap.initial -v  
nmap -A -p- -iL targets -oN nmap.aggressive -v  
nmap -p --script=vuln -v


