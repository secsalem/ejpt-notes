setup msf 
- workspace -a ftp_enum
- search portscan - tcp
- set rhosts 
- run and check open ports 
we know we have port ftp 21 open 
then we check ftp version we found 

msf modules 
/smb/smb_version
/smb/smb_enumusers
/smb/smb_enumshares - set showfiles true 
/smb/smb_login - bruteforce we already have user "admin" based in previous enumshares and set pass_file with unix_passwords.txt
smbclient -L \\\\\\\\192.126.66.3 \\\\ -U  admin        to list shares 
smbclient  \\\\\\\\192.126.66.3 \\\\public -U  admin          to enter share
you can try every share we have 


nmap -sU --top-ports 25 192.126.66.3

nmap --script smb-enum-shares  -p 139 -v 192.61.243.3 will get u the shares 
nmap --script smb-os-discovery.nse -p 445 192.126.66.3
msfconsole / use auxiliary/scanner/smb/smb_version/ set RHOSTS 192.126.66.3 / exploit
nmap --script smb-os-discovery.nse -p 445 192.126.66.3
nmblookup -A 192.126.66.3
smbclient -L 192.126.66.3 -N (null connection because we can see shares from previous investigation)
rpcclient -U "" -N 192.126.66.3 (Anonymous connection is allowed since no errors are thrown while connecting to samba server without any credentials)
nmap scans
--script smb-enum-shares


References: 1. Samba (https://www.samba.org/) 2. smbclient (https://www.samba.org/samba/docs/current/man-html/smbclient.1.html) 3. rpcclient (https://www.samba.org/samba/docs/current/man-html/rpcclient.1.html) 4. nmblookup (https://www.samba.org/samba/docs/current/man-html/nmblookup.1.html) 5. Nmap Script: smb-os-discovery (https://nmap.org/nsedoc/scripts/smb-os-discovery.html) 6. Metasploit Module: SMB Version Detection (https://www.rapid7.com/db/modules/auxiliary/scanner/smb/smb_version)

