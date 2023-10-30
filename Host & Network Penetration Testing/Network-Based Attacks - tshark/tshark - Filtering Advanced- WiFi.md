show only wifi traffic 
- : tshark -r WiFi_traffic.pcap -Y "wlan"


show only  the deauthentication packets?
- tshark -i <interface> -Y "wlan.fc.type_subtype == 0x0c"


Which command can be used to only display WPA handshake packets?
- tshark -i <interface> -Y "eapol"


Which command can be used to only print the SSID and BSSID values for all beacon frames?
- tshark -i <interface> -Y "wlan.fc.type_subtype == 0x08" -T fields -e wlan.bssid -e wlan.ssid



What is BSSID of SSID “LazyArtists”?
- tshark -r WiFi_traffic.pcap -Y "wlan.ssid==LazyArtists" -Tfields -e wlan.bssid

1. `-Y "wlan.ssid==LazyArtists"`: The `-Y` option is used to apply a display filter. In this case, you are filtering for packets where the SSID matches "LazyArtists." This filter will select packets that belong to the specified wireless network.
    
2. `-Tfields`: The `-T` option is used to specify the output format. In this case, you are using "fields" format, which means the output will be in a tabular format with specified fields.
    
3. `-e wlan.bssid`: The `-e` option is used to specify the fields you want to extract from the matching packets. Here, you are extracting the BSSID (Basic Service Set Identifier) field from the packets that match the SSID "LazyArtists."



1. SSID “Home_Network” is operating on which channel?
- tshark -r WiFi_traffic.pcap -Y "wlan.ssid==Home_Network" -Tfields -e wlan_radio.channel

1. `-Y "wlan.ssid==Home_Network"`: The `-Y` option is used to apply a display filter. In this case, you are filtering for packets where the SSID matches "Home_Network." This filter will select packets that belong to the specified wireless network with that SSID.
    
2. `-Tfields`: The `-T` option is used to specify the output format. Here, you are using "fields" format, which means the output will be in a tabular format with specified fields.
    
3. `-e wlan_radio.channel`: The `-e` option is used to specify the fields you want to extract from the matching packets. In this case, you are extracting the "wlan_radio.channel" field. This field represents the channel on which the Wi-Fi communication is taking place for the packets that match the SSID "Home_Network."



1. Which two devices received the deauth messages? State the MAC addresses of both.
- tshark -r WiFi_traffic.pcap -Y "wlan.fc.type_subtype==0x000c" -Tfields -e wlan.ra

1. `-Y "wlan.fc.type_subtype==0x000c"`: The `-Y` option is used to apply a display filter. In this case, you are filtering for packets where the "wlan.fc.type_subtype" field matches the hexadecimal value "0x000c." This filter selects packets that are specifically "Deauthentication" frames. Deauthentication frames are used in Wi-Fi networks to terminate authenticated connections between client devices and access points.
    
2. `-Tfields`: The `-T` option is used to specify the output format. Here, you are using "fields" format, which means the output will be in a tabular format with specified fields.
    
3. `-e wlan.ra`: The `-e` option is used to specify the field you want to extract from the matching packets. In this case, you are extracting the "wlan.ra" field. The "wlan.ra" field represents the Receiver Address (RA) in Wi-Fi frames, which typically corresponds to the MAC address of the client device that is the target of the deauthentication frame.
"wlan.fc.type_subtype==0x000c"
- `wlan`: This part of the filter specifies that we are working with fields related to the WLAN (Wireless Local Area Network) protocol, which is commonly used for Wi-Fi communication.
    
- `fc`: This stands for "frame control," which is a field found in the header of Wi-Fi frames. The frame control field contains several subfields that convey information about the frame type, subtype, and other control information.
    
- `type_subtype`: This is a specific subfield within the frame control field. It represents the type and subtype of the Wi-Fi frame. In Wi-Fi, frame types and subtypes are used to categorize different types of frames based on their purpose and function.
    
- `==`: This operator is used to compare values. In this case, it's used to compare the value of the "wlan.fc.type_subtype" field to the specified value.
    
- `0x000c`: This is the hexadecimal value that we are comparing the "wlan.fc.type_subtype" field to. In hexadecimal notation, "0x" is used as a prefix to indicate that the following digits represent a hexadecimal value. In this context, "0x000c" corresponds to the hexadecimal value for "Deauthentication" frames in Wi-Fi communication.

1. Which device does MAC 5c:51:88:31:a0:3b belongs to? Mention manufacturer and model number of the device.
- : tshark -r WiFi_traffic.pcap -Y "wlan.ta==5c:51:88:31:a0:3b && http" -Tfields -e http.user_agent

1. `-Y "wlan.ta==5c:51:88:31:a0:3b && http"`: The `-Y` option is used to apply a display filter. In this case, you are applying a complex filter using the logical AND operator `&&`. This filter does the following:
    
    - `wlan.ta==5c:51:88:31:a0:3b`: The first part of the filter filters for packets where the "wlan.ta" field matches the MAC address "5c:51:88:31:a0:3b." The "wlan.ta" field typically represents the transmitter address in Wi-Fi frames, so this part of the filter selects packets transmitted by the device with that MAC address.
    - `http`: The second part of the filter selects packets that contain HTTP traffic. It filters for packets where the protocol is HTTP.
2. `-Tfields`: The `-T` option is used to specify the output format. Here, you are using "fields" format, which means the output will be in a tabular format with specified fields.
    
3. `-e http.user_agent`: The `-e` option is used to specify the field you want to extract from the matching packets. In this case, you are extracting the "http.user_agent" field. The "http.user_agent" field typically contains information about the user-agent string sent by a web client in its HTTP request header. It can provide details about the client's web browser or application.

