tshark -h 


display what kind of protocols in the pcap file 
- tshark -r HTTP_traffic.pcap -qz io,phs 
io = input and out put 
phs =  stands for "protocol hierarchy statistics

filter on what type of protocol 
- tshark -r HTTP_traffic.pcap -Y http

Command to show only the IP packets sent from IP address 192.168.252.128 to IP address 52.32.74.91?
- tshark -i <interface> -Y "ip.src == 192.168.252.128 && ip.dst == 52.32.74.91" 

To display only the HTTP GET requests
- tshark -i <interface> -Y "http.request.method == GET"

To print only the source IP and URL for all HTTP GET request packets
- tshark -r HTTP_traffic.pcap -Y "http.request.method==GET" -Tfields -e frame.time -e ip.src -e http.request.full_uri

to know how many packet contains password string 
- tshark -r HTTP_traffic.pcap -Y "http contains password"


What is the destination IP address for GET requests sent for New York Times (www.nytimes.com)
- tshark -r HTTP_traffic.pcap -Y "http.request.method==GET && http.host==www.nytimes.com" -Tfields -e ip.dst



What is the session ID being used by 192.168.252.128 for Amazon India store (amazon.in)
- tshark -r HTTP_traffic.pcap -Y "ip contains amazon.in && ip.src==192.168.252.128" -Tfields -e ip.src -e http.cookie


get OS machine type of src ip
- tshark -r HTTP_traffic.pcap -Y "ip.src==192.168.252.128 && http" -Tfields -e http.user_agent