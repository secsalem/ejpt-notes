

- gobuster dir -u http://192.24.193.3/ -w  /usr/share/wordlists/seclists/Discovery/Web-Content/raft-medium-directories-lowercase.txt

- gobuster dir -u http://192.156.207.3 -w /usr/share/wordlists/dirb/common.txt -b 403,404 -x .php,.xml,.txt -r


if you found interesting directory for example /data 
just add it to the next bruteforce