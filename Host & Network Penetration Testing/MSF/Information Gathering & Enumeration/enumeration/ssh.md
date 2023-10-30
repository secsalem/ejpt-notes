- auxiliary/scanner/ssh/ssh_version
- auxiliary/scanner/ssh/ssh_enumusers
- we look for usernames first 
- auxiliary/scanner/ssh/ssh_login
- we bruteforce the usernames we found and open mterpter sessions

after we find the username and password we can open these commands to know what's the running sessions 
- sessions 
we can then change to the first opened session which is meterpter session from our bruteforce we did because each username and password found it will open a meterpeter session
- sessions -i (number of session)