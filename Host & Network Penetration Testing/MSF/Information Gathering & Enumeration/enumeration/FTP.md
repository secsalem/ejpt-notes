setup msf 
- workspace -a ftp_enum
- search portscan - tcp
- set rhosts 
- run and check open ports 
we know we have port ftp 21 open 
then we check ftp version we found 

use auxiliary/scanner/ftp/ftp_version to check version
- search proftpd if there is any read exploits else bruteforce 

- auxiliary(scanner/ftp/ftp_login) bruteforce login
-  /usr/share/metasploit-framework/data/wordlists/common_users.txt 
-  /usr/share/metasploit-framework/data/wordlists/unix_passwords.txt

we can test anoymous login 
- scanner/ftp/anonymous modules 