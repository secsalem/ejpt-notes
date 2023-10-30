rpcclient 
srvinfo will give us os version 
enumdomusers 

enumlinux -o to get OS information 
enum4linux -U 192.150.34.3

msfconsole /scanner/smb/smb2

Server Info

- **Server Info**: `srvinfo`

Users enumeration

- **List users**: `querydispinfo` and `enumdomusers`
    
- **Get user details**: `queryuser <0xrid>`
    
- **Get user groups**: `queryusergroups <0xrid>`
    
- **GET SID of a user**: `lookupnames <username>`
    
- **Get users aliases**: `queryuseraliases [builtin|domain] <sid>`


for more commands of (groups, aliasgroups, domains, shares, SID's) enumeration 
https://book.hacktricks.xyz/network-services-pentesting/pentesting-smb/rpcclient-enumeration

samba main site  - rpcclients 
https://www.samba.org/samba/docs/current/man-html/rpcclient.1.html