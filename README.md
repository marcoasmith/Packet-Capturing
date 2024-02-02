<h1>Packet Captures Using Wireshark</h1>



<h2>Description</h2>
To capture and analyze network traffic using Wireshark, start by identifying the wired interface for packet capture, typically named starting with 'en'. Once Wireshark is open, use its controls to begin capturing packets on the selected ethernet port. To save the captured data for analysis, you must first stop the capture, as Wireshark only allows saving after capturing has ceased. For specific analysis, such as isolating HTTPS traffic, apply a display filter with the condition tcp.port == 443. If you're interested in identifying visits to a particular webpage, use a TLS handshake filter tls.handshake.type == 1 to pinpoint the start of a secure session, and then filter by the website's IP address using ip.addr == 142.251.163.104 to gather relevant packet information. In cases where you want to exclude traffic to a specific IP address while focusing on HTTPS packets, employ a conditional statement in the filter, such as !(ip.addr == 142.251.163.104) and tcp.port == 443. For more complex filtering that involves both standard HTTP and HTTPS traffic while excluding a certain IP, use a compound conditional statement like !(ip.addr == 142.251.163.104) and (tcp.port == 80 or tcp.port == 443), ensuring to encapsulate conditions within parentheses to correctly prioritize the evaluation order. This approach facilitates the targeted analysis of network traffic, allowing for the extraction of detailed information about web page visits and HTTPS communications while excluding specific unwanted data.
<br />


<h2>Technologies and Utilities Used</h2>

- <b>Wireshark</b> 
- <b>Firefox</b>

<h2>Environments Used </h2>

- <b>Ubuntu</b>

<h2>Lab walk-through:</h2>



Filter 1: <br/>
![image](https://github.com/marcoasmith/Packet-Capturing/assets/155500497/22a33d00-bfba-4c2e-a68d-346af8a34e3b)


<img src="" height="80%" width="80%" alt=""/>
<br />
<br />

Filter 2: <br/>
![image](https://github.com/marcoasmith/Packet-Capturing/assets/155500497/f1a031b7-faf9-4f79-aba8-4fb813f96b51)

<img src="" height="80%" width="80%" alt=""/>
<br />
<br />

Filter 3: <br/>
![image](https://github.com/marcoasmith/Packet-Capturing/assets/155500497/53f631c7-a0e5-4ba1-b434-ddaa567b9710)



<img src="" height="80%" width="80%" alt=""/>
<br />
<br />

Filter 4: <br/>
![image](https://github.com/marcoasmith/Packet-Capturing/assets/155500497/fe253faa-7b28-4020-adb3-ce30ca2c92b4)



<img src="" height="80%" width="80%" alt=""/>
<br />
<br />

Filter 5: <br/>
![image](https://github.com/marcoasmith/Packet-Capturing/assets/155500497/3799132a-0d29-42e1-bcb0-0c31d4eda6a4)




<img src="" height="80%" width="80%" alt=""/>
<br />
<br />
