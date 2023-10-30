: nc 192.80.153.3 25

Q3. Does user “admin” exist on the server machine? Connect to SMTP service using netcat and check manually. 
Answer: Yes 
Command: VRFY admin@openmailbox.xyz 

Q4. Does user “commander” exist on the server machine? Connect to SMTP service using netcat and check manually. 
Answer: No 
Command: VRFY commander@openmailbox.xyz

Q5. What commands can be used to check the supported commands/capabilities? 
Connect to SMTP service using telnet and check. 
Commands: 
- telnet 192.26.29.3 25
- HELO attacker.xyz 
- EHLO attacker.xyz

Q6. How many of the common usernames present in the dictionary /usr/share/commix/src/txt/usernames.txt exist on the server. Use smtp-user-enum tool for this task. 
Answer: 8 
Command: smtp-user-enum -U /usr/share/commix/src/txt/usernames.txt -t 192.80.153.3


Q7. How many common usernames present in the dictionary /usr/share/metasploit-framework/data/wordlists/unix_users.txt exist on the server. Use suitable metasploit module for this task. 
Answer: 20 
Commands: msfconsole use auxiliary/scanner/smtp/smtp_enum set RHOSTS 192.80.153.3 Exploit


Q8. Connect to SMTP service using telnet and send a fake mail to root user. Commands:
```
telnet 192.26.29.3 25
HELO attacker.xyz 
mail from: admin@attacker.xyz 
rcpt to:root@openmailbox.xyz 

data
Subject: Hi Root 
Hello, 
This is a fake mail sent using telnet command. 
From, 
Admin


.

```

Note: There is a dot(.) in the last line which indicates the termination of data.


Q9. Send a fake mail to root user using sendemail command. 
Command: 

```sendemail -f admin@attacker.xyz -t root@openmailbox.xyz -s 192.26.29.3 -u Fakemail -m "Hi root, a fake from admin" -o tls=no```
