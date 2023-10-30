ip a 
nmap --script smb-os-discovery.nse -p445$ $IP

______________________________
msfconsole
use auxiliary/scanner/smb/smb_version

____________________________
NetBIOS over TCP/IP client used to lookup NetBIOS names
nmblookup -A $IP 

_______________________
ftp-like client to access SMB/CIFS resources on servers
smbclient -L $IP -N (null session} )

______________________________
tool for executing client side MS-RPC functions
rpcclient -U "" -N $IP