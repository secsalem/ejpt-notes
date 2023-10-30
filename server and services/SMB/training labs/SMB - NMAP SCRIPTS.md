smb 445 port 

--script smb-protocols  | version information 
--script smb-security-mode | acount used etc
--script smb-enum-sessions | who logged in 
--script smb-enum-sessions --script-args smbusername=admin , smbpassword=smbserver_771 | pass arguments 
--script smb-enum-shares | what do we have access to ? we can also add --script-args after authenticating to get better results of shares access 
--script smb-enum-users | to know which users exist we can parse --script-args
--script smb-server-stats | get server statistics we can parse --script-args [admin:pass]
--script smb-enum-domains | we could see users/passwords enum 
--script smb-enum-services | information specific to the service 
--script smb-enum-shares,smb-ls | will get shares and will run ls command on them with --script-args 
