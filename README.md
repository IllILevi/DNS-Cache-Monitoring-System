# DNS-Cache-Monitoring-System
This is a Windows OS-level DNS cache monitoring system that runs a PowerShell script to access your DNS cache, then a python file calls the Virus Total API to check each unique DNS for malware and logs malicious detections to Windows Event Viewer. This is done automatically via the Windows Task Scheduler.

## Requirments:
1. Windows 10 or 11
2. Python 3.9+ installed
3. VirusTotal API Key
4. Administrator privelages

## How It Works
TODO: EXPLAIN HOW EACH COMPONENT WORKS

## Setup Instructions

### 1. Clone respository
git clone https://github.com/IllILevi/DNS-Cache-Monitoring-System

### 2. Install python dependencies
pip install -r requirements.txt

### 3. Set your VirusTotal API key
setx API_KEY "your_api_key_here"

### 4. Register the Event Log source (run PowerShell as Administrator)
New-EventLog -LogName Application -Source DNS_Monitor

### 5. Task Scheduler


## Viewing Alerts
The malicious IP detections appear in Event Viewer -> Windows Logs -> Application
Look for entries with: Source: DNS_Monitor and Event ID: 1001


