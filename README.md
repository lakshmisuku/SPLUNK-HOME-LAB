# SPLUNK-HOME-LAB
PROJECT OVERVIEW

This project demonstrates the simulation and detection of brute force attacks within a contorlled SOC lab environment. An Ubuntu server was configured with multiple exposed services and authentication logs were centrally monitored using Splunk.

The objective was to analyze attacker behavior and implement detection logic aligned with real-world SOC monitoring practices.

LAB ENVIRONMENT

Attacker Machine: Kali Linux

Target Machine: Ubuntu Server

Services Tested: SSH, FTP, Apache Web Server

SIEM Platform: Splunk Enterprise

Log Collection: Splunk Universal Forwarder

All authentication and web logs were forwarded to Splunk for centralized visibility and analysis.

SERVICE DISCOVERY AND ATTACK SURFACE IDENTIFICATION

The environment was assessed to identify exposed services and open ports. The following services were discovered:
* SSH for remote access
* FTP for file transfer
* Web application hosting a login page

This established the attack surface for brute force simulations.

SSH AUTHENTICATION MONITORING

Repeated login attempts were simulated against the SSH service to replicate brute force behavior.

System authentication logs recorded multiple failed login attempts from the same source. Within Splunk, detection logic was implemented to identify:
* High frequency login failures.
* Repeated attempts from a single IP address.
* Authentication spikes within short time intervals.

Threshold-based alerting was configured to flag suspicious activity.

FTP LOGIN ACTIVITY ANALYSIS

Brute force activity targeting the FTP service generated repeated authentication failures.

Log analysis in Splunk focused on:
* Source IP correlation
* Frequency of failed login attempts
* Abnormal login behavior patterns

This demonstrated monitoring capability across multiple authentication services.

WEB APPLICATION LOGIN MONITORING

A web login page hosted on Apache was used to simulate credential guessing attacks.

Web server logs revealed:
* Repeated POST requests to the login endpoint
* Multiple authentication failures
* High request volume from a single client

Detection rules were developed to identify abnormal login behavior indicative of HTTP brute force attacks.

ACCOUNT COMPROMISE DETECTION LOGIC

Advanced analysis included identifying scenarios where multiple failed authenthication attempts were followed by a successful login.

Such patterns may indicate successful credential compromise. Detection queries were designed to correlate failed and successful login events within defined time windows.

SECURITY HARDENING MEASURES

Following the attack simulations, defensive improvements were implemented:

* Account lockout policies.
* Restriction of privileged access.
* Strengthened configurations.
* Login rate limiting.
* Enhanced log monitoring.

These measures demonstrated practical mitigation strategies against brute force attacks.

SKILLS DEMONSTRATED

* Multi-service log analysis.
* Brute force attack pattern recognition.
* SIEM integration using Splunk.
* Threshold-based detection rule creation.
* Event correlation and alert configuration.
* SOC monitoring workflow simulation.

FUTURE IMPROVEMENTS

* Creating a simple Splunk dashboard to visualize failed login trends.
* Creating seperate alerts for SSH, FTP and web attacks.
* Monitoring successful logins after multiple failures more closely.
* Expanding the lab to include multiple target machines.
* Improving alert accuracy to reduce false positives.

PROJECT OUTCOME

This project reflects hands-on experience in simulating authentication-based attacks developing detection mechanisms within a SIEM platform. It demonstrates an understanding of attack methodologies, log analysis and SOC-level monitoring practices.

![ATTACKER](https://github.com/user-attachments/assets/60b96393-b70c-406f-a9b7-2dc12b0d5ac4)
![ALERTS](https://github.com/user-attachments/assets/2b42c4f1-cc37-4468-b10f-f572d6dcfb15)
![BRUTE FORCE ATTACK](https://github.com/user-attachments/assets/cc5b23d7-9ef4-40a4-b9f0-e93ea3ba4347)
![FTP ANONYMOUS LOGIN](https://github.com/user-attachments/assets/923c7a16-2b9a-44cc-95ac-3e643a8ca145)
![WEB PAGE BRUTE FORCE ATTACK](https://github.com/user-attachments/assets/a8e0bf5e-9f3f-4afe-bef8-a53cf3a467a6)
