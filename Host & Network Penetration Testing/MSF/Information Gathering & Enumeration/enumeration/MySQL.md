


- auxiliary/scanner/mysql/mysql_version
- auxiliary/scanner/mysql/mysql_login
	- set PASS_FILE /usr/share/metasploit-framework/data/wordlists/unix_passwords.txt
	- set USER_FILE /usr/share/metasploit-
	- normally its root user 
- auxiliary/admin/mysql/mysql_enum
	- needs username and password
- auxiliary/admin/mysql/mysql_sql
	- needs username and password
	- SQL query
		- set SQL show databases;
		- set SQL use videos; (name of database)
		- other commands SQL etc.. 
- auxiliary/scanner/mysql/mysql_file_enum
	- needs username and passwords and file_list
- auxiliary/scanner/mysql/mysql_hashdump
	- needs username and password
- auxiliary/scanner/mysql/mysql_schemadump
	- needs username and password
- auxiliary/scanner/mysql/mysql_writable_dirs
	- needs username and password and DIR_LIST /data/wordlist/directories.txt

to connect via mysql command
- mysql -h 192.128.23.3 -u root -p
- 

