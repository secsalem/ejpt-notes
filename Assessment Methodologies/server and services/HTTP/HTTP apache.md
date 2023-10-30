nmap -p 80 --scipt banner 

msfconsole
	http/http_version 
	http/brute_dirs -> directories
	http/robots_txt

curl http://192.119.197.3/index | more

wget "http://ip/index"

lynx http://ip

dirb ip wordlist 

192.119.197.3