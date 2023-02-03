# I - THE DANGER

## 1-1 War stories
### 1.1.1 HIJACKING
```bash
	A hijacking attack is an attacks accurs when an attackers set up a rogue wireless hostpots, in other way an evil twin attack by taking down the original hostpots and making another one with the same SSID so that people can connect with this as trusted, wich allow the attacker to see all the trafic and take password sessions ...
```
### 1.1.2 RANSOMED COMPANIES
	An example of a ransome war by a phishing attack, when an attacker pretended to be the CEO and sent a PDF to all the employees the pdf allow the attacker to access the network and crypte all the assets and data untill a ransom is paid.
## 1-3 THREAT IMPACT
### 1.3.1 PII, PHI and PSI
```bash
	Personally identifiable information (PII) is any information that can be used to positively identify an individual.
	protected health information (PHI) are the medical record for patients about their health and medicals that they take ...
	Personal security information (PSI) This information includes usernames, passwords... that individuals use to access information or services on the network.
```
# II - FIGHTERS IN THE WAR

## 2-1 THE MODERN SOC
### 2.1.1 ELEMENTS OF THE SOC
```bash
	The major elemnts of the SOC are : People, Processes, and Thechnology
```
### 2.1.2 PEOPLE AND PROCESS IN THE SOC
```bash
	SOC Level 1 : Alert Analyst, check the alert if there is a real incident, if so they report it to Level 2
	SOC Level 2 : Incident Responder, Take the required actions and realise the incident response plan
	SOC Level 3 : Threat Hunter, They trace the process of the malware to determine its impact and how it can be prevented/removed
	SOC Manager : Manage all the ressource of the SOC, and the point of contact with company's and customers
```
### 2.1.4 TECH IN THE SOC : SIEM
```bash
	The security operation center needs a security information and event management system (SIEM) the SIEM make sense of all the coming data, it may include : 
	+ Event collection, correlation, and analysis
	+ Security monitoring
	+ Endpoint Data 
	+ System logs
	+ Network Traffic
	+ Vulnerability tracking
	+ Threat intelligence
```
### 2.1.5 TECH IN THE SOC : SOAR
```bash
	SIEM systems necessarily produce more alerts than most SecOps teams can realistically investigate, SOAR will process many of these alerts automatically
	The security orchestration, automation and response (SOAR) and the SIEM are often together to complete each other
	SOAR impliment incident investigation and response workflows based on playbooks developed by the security team.
	SOAR => Security | Orchestration | Automation | Response
	+ Orchestration => Create a custum platform to manage security tools and resources
	+ Automation => Execution of the security process with the less human interaction
	+ Response => Execution of security procedures based on a planification and a playbook to address specific types of events
```
### 2.1.6 SOC METRICS
```bash
	+ Dwell Time : The time the attacker could time to access the network before hi's detected/stoped
	+ Mean Time to Detect : The time the SOC realise that a real incident occured
	+ Mean Time to Respond : The time taken to stop an incident
	+ Mean Time to Contain : The time to stop an incident to cuz more damage
	+ Time to control : The time to stop the malware from spreading in the NET
```
### 2.1.8 SECURITY & AVAILABILITY
```bash
	Each business or industry has a limited tolerance for network downtime.
	AVAILABILITY				DOWNTIME
	
	Three nines				8.76 hours
	Four nines				52.56 minutes
	Five nines				5.256 minutes
	Six nines				31.56 seconds
	Seven nines				3.16 seconds
```
