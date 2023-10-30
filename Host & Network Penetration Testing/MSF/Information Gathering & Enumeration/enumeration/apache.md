when search for modules 
- search type: auxiliary name:http

- auxiliary/scanner/http/apache_userdir_enum
- auxiliary/scanner/http/brute_dirs
- auxiliary/scanner/http/dir_scanner
- auxiliary/scanner/http/dir_listing
- auxiliary/scanner/http/http_put
		-use auxiliary/scanner/http/http_put 
		set RHOSTS 192.111.169.3 
		set PATH /data 
		set FILENAME test.txt 
		set FILEDATA "Welcome To AttackDefense" run
- auxiliary/scanner/http/files_dir
- auxiliary/scanner/http/http_login
- auxiliary/scanner/http/http_header
- auxiliary/scanner/http/http_version
- auxiliary/scanner/http/robots_txt
	- you will check dir where you can or cant enter so you can bruteforce manually




