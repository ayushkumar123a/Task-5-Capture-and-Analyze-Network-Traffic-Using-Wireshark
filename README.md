🛠 Tools Required
•	Wireshark (for .pcapng analysis)
•	Provided .pcapng file containing captured traffic
•	CISA Spring4Shell vulnerability advisory
•	Company infrastructure & team contact list
________________________________________
✅ Steps to Complete
🔹 Step 1: Analyze Network Traffic (task1.pcapng)
•	Open the .pcapng file in Wireshark
•	Filter suspicious traffic using filters like:
javascript
CopyEdit
http
tcp.port == 8080
ip.src == <suspicious IP>
•	Look for signs of exploitation:
o	HTTP POST/GET requests to / or unusual endpoints
o	Shell commands or malicious payloads in request bodies
o	Requests targeting Spring Framework-based servers
________________________________________
🔹 Step 2: Match with Affected Infrastructure
•	The logs show traffic between an external IP and the Product Development Staging Server on port 8080 (Tomcat).
•	The staging server runs Spring Framework 5.3.17 — vulnerable to CVE-2022-22965 (Spring4Shell).
•	This server is critical for internal product testing and pre-deployment.
________________________________________
🔹 Step 3: Determine Severity
•	Severity: Critical
o	Vulnerability allows Remote Code Execution (RCE)
o	Service downtime and compromised integrity detected
o	Possible attacker control over staging environment

