enum and connect 
nc $ip 22
ssh root@ip 
nmap $IP -p 22 --script ssh2-enum-algos |  number of algorithms (for encryption, compression, etc.) that the target SSH2 server offers

if we want to get rsa host key 
- nmap $ip  -p 22 --script  ssh-hostkey --scripit-args ssh_hostkey=full  | Shows the target SSH server's key fingerprint
- nmap $ip  -p 22 --script  ssh-auth-methods --scripte-args="ssh.user=student"

 