

- dirb http://192.45.178.3
- curl -X GET 192.45.178.3
- curl -I 192.45.178.3
- : curl -X OPTIONS 192.45.178.3
- curl -X POST 192.45.178.3
- curl -XPUT 192.45.178.3
- curl -X OPTIONS 192.45.178.3/login.php
- curl -X POST 192.45.178.3/login.php
- curl -X POST 192.45.178.3/login.php -d "name=john&password=password" -v
- curl -X OPTIONS 192.45.178.3/post.php
- curl -X OPTIONS 192.45.178.3/uploads/
- curl -X OPTIONS 192.45.178.3/uploads/ -v
- echo "Hello World" > hello.txt 
- curl 192.45.178.3/uploads/ --upload-file hello.txt
- curl -XDELETE 192.45.178.3/uploads/hello.txt
- 