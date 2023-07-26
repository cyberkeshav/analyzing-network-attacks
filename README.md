<h1>Analyzing Network Attacks</h1>

<h2>Description</h2>

In this specific task, I was asked to go through the following scenario and answer two questions in the end: <br />

You work as a security analyst for a travel agency that advertises sales and promotions on the company’s website. The employees of the company regularly access the company’s sales webpage to search for vacation packages their customers might like. <br />

One afternoon, you receive an automated alert from your monitoring system indicating a problem with the web server. You attempt to visit the company’s website, but you receive a connection timeout error message in your browser.<br />

You use a packet sniffer to capture data packets in transit to and from the web server. You notice a large number of TCP SYN requests coming from an unfamiliar IP address. The web server appears to be overwhelmed by the volume of incoming traffic and is losing its ability to respond to the abnormally large number of SYN requests. You suspect the server is under attack by a malicious actor. <br />

You take the server offline temporarily so that the machine can recover and return to a normal operating status. You also configure the company’s firewall to block the IP address that was sending the abnormal number of SYN requests. You know that your IP blocking solution won’t last long, as an attacker can spoof other IP addresses to get around this block. You need to alert your manager about this problem quickly and discuss the next steps to stop this attacker and prevent this problem from happening again. You will need to be prepared to tell your boss about the type of attack you discovered and how it was affecting the web server and employees. <br />

Questions to be answered:
1: Identify the type of attack that may have caused this 
network interruption
2: Explain how the attack is causing the website malfunction

<br />

<h2>Resources Used</h2>

- <b>Wireshark TCP_HTTP log</b> 

<h2>Identify the type of attack that may have caused this 
network interruption</h2>
  
One possible reason for the website's connection timeout error message is a Denial of Service (DoS) attack. The logs indicate that the web server becomes unresponsive when inundated with an excessive number of SYN packet requests. This occurrence aligns with a specific type of DoS attack known as SYN flooding.

<h2>Explain how the attack is causing the website malfunction</h2>

When users attempt to connect to the web server, a three-way handshake process takes place using the TCP protocol. This handshake comprises three steps:

1. The source sends a SYN packet to the destination, requesting to initiate a connection.
2. The destination responds to the source with a SYN-ACK packet, acknowledging the connection request and reserving resources for the upcoming connection.
3. The source acknowledges the permission to connect by sending a final ACK packet to the destination.

However, during a SYN flood attack, a malicious actor inundates the server with an excessive number of SYN packets simultaneously, depleting the available resources reserved for connections. Consequently, the server is left with no resources to handle legitimate TCP connection requests.

As evident from the logs, the web server has been overwhelmed by the influx of SYN requests, rendering it unable to process further connection attempts from users. Consequently, visitors experience connection timeout errors, as the server is incapable of establishing new connections.
