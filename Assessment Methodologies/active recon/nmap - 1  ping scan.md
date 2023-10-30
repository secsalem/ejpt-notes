first we should identify how many ports we have in the system 
-sn :Ping Scan - disable port scan
sudo nmap -sn 10.0.2.15/24 
then we can proceed doing port scans on the targets we have 
or netdiscover 
sudo netdiscover -i eth0 -r 10.0.2.15/24