

- nikto -h 192.168.4.3
- analyze vulnerabilities , we are looking for LFI vulnerability 
- nikto -h http://192.230.148.3/index.php?page=arbitrary-file-inclusion.php -Tuning 5 -Display V
- nikto -h http://192.230.148.3/index.php?page=arbitrary-file-inclusion.php -Tuning 5 -o nikto.html -Format htm
- file:///root/nikto.html
- 