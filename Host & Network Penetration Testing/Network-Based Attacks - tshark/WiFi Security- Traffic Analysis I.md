

- (wlan.fc.type_subtype == 0x0008) && (!(wlan.wfa.ie.wpa.version == 1)) && !(wlan.tag.number == 48)

1. `(wlan.fc.type_subtype == 0x0008)`: This part of the filter checks for the frame control field's type and subtype to identify Data frames. The value `0x0008` corresponds to the Data frame subtype. This filter will capture Data frames.
    
2. `&& (!(wlan.wfa.ie.wpa.version == 1))`: This part of the filter excludes frames where the WPA version is 1. It filters out WPA (Wi-Fi Protected Access) frames with version 1.
    
3. `&& !(wlan.tag.number == 48)`: This part of the filter excludes frames that have an information element (IE) with a tag number of 48. Information elements provide additional information about the Wi-Fi network and its capabilities.

Q2. The SSID 'Home_Network' is operating on which channel?
A. 6 
Filter: wlan contains Home_Network

Q3. Which security mechanism is configured for SSID 'LazyArtists'? Your options are: OPEN, WPA-PSK, WPA2-PSK.
A. WPA2-PSK 
Filter: wlan contains LazyArtists

Q4. Is WiFi Protected Setup (WPS) enabled on SSID 'Amazon Wood'? State Yes or No.
A. Yes 
Filter: (wlan.ssid contains "Amazon") && (wlan.fc.type_subtype == 0x0008)
```
The filter `(wlan.ssid contains "Amazon") && (wlan.fc.type_subtype == 0x0008)` is a Wireshark display filter used to capture and display Wi-Fi network traffic that meets specific criteria. Let's break down each part of the filter:

1. `(wlan.ssid contains "Amazon")`: This part of the filter checks if the SSID (Service Set Identifier) of the Wi-Fi network contains the string "Amazon." The SSID is the name of the Wi-Fi network that devices connect to. The `contains` keyword is used to check if the SSID includes the specified text.
    
2. `&&`: The double ampersand (`&&`) is a logical AND operator used to combine multiple conditions. It ensures that both conditions on either side of the operator must be true for the filter to match.
    
3. `(wlan.fc.type_subtype == 0x0008)`: This part of the filter checks if the type and subtype fields of the WLAN (Wireless LAN) frame control match the value `0x0008`. In Wireshark's context, this value corresponds to Data frames. Data frames are used to carry actual network data between devices on a Wi-Fi network.
```

Q5. What is the total count of packets which were either transmitted or received by the device with MAC e8:de:27:16:87:18? 
A: 5701
Filter: (wlan.ta == e8:de:27:16:87:18) || (wlan.ra == e8:de:27:16:87:18)

```
1. `(wlan.ta == e8:de:27:16:87:18)`: This part of the filter checks if the transmitter address (TA) of the WLAN (Wireless LAN) frame matches the MAC address `e8:de:27:16:87:18`. The transmitter address is the MAC address of the device that sent the frame.
    
2. `||`: The double vertical bar (`||`) is a logical OR operator used to combine multiple conditions. It means that if either of the conditions on either side of the operator is true, the filter will match.
    
3. `(wlan.ra == e8:de:27:16:87:18)`: This part of the filter checks if the receiver address (RA) of the WLAN frame matches the MAC address `e8:de:27:16:87:18`. The receiver address is the MAC address of the device that is intended to receive the frame.
```



Q6. What is the MAC address of the station which exchanged data packets with SSID 'SecurityTube_Open'?
A: 5c:51:88:31:a0:3b 
SSID SecurityTube_Open is hosted on BSSID e8:de:27:16:87:18. 
Filter: ((wlan.bssid == e8:de:27:16:87:18) ) && (wlan.fc.type_subtype == 0x0020)

```
1. `((wlan.bssid == e8:de:27:16:87:18) )`: This part of the filter checks if the BSSID of the Wi-Fi network matches the MAC address `e8:de:27:16:87:18`. The BSSID is the MAC address of the Wi-Fi access point (AP) that serves as the center of a basic service set (BSS) in a wireless network.
    
2. `&&`: The double ampersand (`&&`) is a logical AND operator used to combine multiple conditions. It means that both conditions on either side of the operator must be true for the filter to match.
    
3. `(wlan.fc.type_subtype == 0x0020)`: This part of the filter checks if the type and subtype fields of the WLAN (Wireless LAN) frame control match the value `0x0020`. In Wireshark's context, this value corresponds to Probe Response frames. Probe Response frames are sent by Wi-Fi access points in response to Probe Request frames from client devices.
```


Q7. From the last question, we know that a station was connected to SSID
'SecurityTube_Open'. Provide TSF timestamp of the association response sent from the
access point to this station.
A. 115152625
Filter: (((wlan.bssid == e8:de:27:16:87:18)) && (wlan.addr==5c:51:88:31:a0:3b)) &&
(wlan.fc.type_subtype == 0x0001)

```
1. `(((wlan.bssid == e8:de:27:16:87:18)) )`: This part of the filter checks if the BSSID of the Wi-Fi network matches the MAC address `e8:de:27:16:87:18`. This means it's looking for frames that involve the specified access point.
    
2. `&&`: The double ampersand (`&&`) is a logical AND operator used to combine multiple conditions. It means that all conditions on both sides of the operator must be true for the filter to match.
    
3. `(wlan.addr==5c:51:88:31:a0:3b)`: This part of the filter checks if the MAC address of the device (transmitter or source address) matches `5c:51:88:31:a0:3b`. This means it's looking for frames originating from or sent by this specific device.
    
4. `&&`: Another logical AND operator that continues combining conditions.
    
5. `(wlan.fc.type_subtype == 0x0001)`: This part of the filter checks if the type and subtype fields of the WLAN (Wireless LAN) frame control match the value `0x0001`. In Wireshark's context, this value corresponds to Management frames with the subtype "Association Request." Association Request frames are sent by client devices to request association with an access point.
```



source : 
https://assets.ine.com/labs/ad-manuals/walkthrough-1141.pdf