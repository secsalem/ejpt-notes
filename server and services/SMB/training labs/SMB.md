server message block -  protocol
SMB uses either **IP port 139 or 445**. Port 139: SMB originally ran on top of NetBIOS using port 139.
windows machine example 
we run
- ipconfig 
1 get IP and subnet mask 

2 run nmap get the open ports 
- nmap -T4 10.6.16.220/20 --open 

3 do service enumeration on services 
- nmap 10.6.16.220 -T4 -sV -O 
- nmap 10.6.16.220 -sC -sV 

we can connect smb mapping network by command 

first to delete any network mapping connections 

- net use * /delete 

to connect smbserver  

- net use Z:\\\\\10.4.17.133\\C$ smbserver_771 /user:adminstrator 

