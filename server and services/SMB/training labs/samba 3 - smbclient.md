
use different tools 

nmap script 
msfconsole smb_enumshares 
enum4linux 
smbclient we can connect to certain file using IP/directory 
- smbclient //IP/directory -N
- smbclient //192.5.121.3/Public -N | to connect to file that have the read and write permissions 

https://www.samba.org/samba/docs/current/man-html/smbclient.1.html

rpcclient
- netshareenumall
Enumerate all shares
https://www.samba.org/samba/docs/current/man-html/rpcclient.1.html

