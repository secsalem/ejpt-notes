nmap -sV -sC IP
nmap scripts 
--script=http-enum 
hydra -L/common_users t -P /common_passwords IP http-get /webdav/ 
davtest -url http://10.2.17.124/webdav
cadaver --help 
cadaver 

davtest -auth bob:password_123321 -url http://10.6.26.128/webdav
