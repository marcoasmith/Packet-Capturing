<h1>Packet Capture Using Wireshark</h1>



<h2>Description</h2>
To capture and analyze network traffic using Wireshark, start by identifying the wired interface for packet capture, typically named starting with 'en'. Once Wireshark is open, use its controls to begin capturing packets on the selected ethernet port. To save the captured data for analysis, you must first stop the capture, as Wireshark only allows saving after capturing has ceased. For specific analysis, such as isolating HTTPS traffic, apply a display filter with the condition tcp.port == 443. If you're interested in identifying visits to a particular webpage, use a TLS handshake filter tls.handshake.type == 1 to pinpoint the start of a secure session, and then filter by the website's IP address using ip.addr == 142.251.163.105 to gather relevant packet information. In cases where you want to exclude traffic to a specific IP address while focusing on HTTPS packets, employ a conditional statement in the filter, such as !(ip.addr == 8.43.85.97) and tcp.port == 443. For more complex filtering that involves both standard HTTP and HTTPS traffic while excluding a certain IP, use a compound conditional statement like !(ip.addr == 8.43.85.97) and (tcp.port == 80 or tcp.port == 443), ensuring to encapsulate conditions within parentheses to correctly prioritize the evaluation order. This approach facilitates the targeted analysis of network traffic, allowing for the extraction of detailed information about web page visits and HTTPS communications while excluding specific unwanted data.
<br />


<h2>Technologies and Utilities Used</h2>

- <b>Wireshark</b> 
- <b>Firefox</b>

<h2>Environments Used </h2>

- <b>Ubuntu</b>

<h2>Lab walk-through:</h2>


<p align="center">
Filter 1: <br/>
<img src="" height="80%" width="80%" alt=""/>
<br />
<br />

<img src="![image](https://github.com/marcoasmith/Packet-Capturing/assets/155500497/a2f33078-e902-4cda-aebf-3ec3f823a446)
" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Enter the number of passes: <br/>
<img src="https://i.imgur.com/nCIbXbg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Confirm your selection:  <br/>
<img src="https://i.imgur.com/cdFHBiU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Wait for process to complete (may take some time):  <br/>
<img src="https://i.imgur.com/JL945Ga.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Sanitization complete:  <br/>
<img src="https://i.imgur.com/K71yaM2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Observe the wiped disk:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
