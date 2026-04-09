# DNS-Cache-Monitoring-System
This is a Windows OS-level DNS cache monitoring system that runs a PowerShell script to access your DNS cache, then a python file calls the Virus Total API to check each unique DNS for malware and logs malicious detections to Windows Event Viewer. This is done automatically via the Windows Task Scheduler.  

TODO: EXPLAIN WHY THIS PROGRAM IS IMPACTFUL

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

### 5. Setting up Task Scheduler
Create a new task  
<img width="353" height="314" alt="Image" src="https://github.com/user-attachments/assets/7f55c47d-abbc-447f-82df-b7b7a900a53b" />  

In the "General" tab, be sure to check the boxes to run with the highest priveleages and whether the user is logged on or not.

In the "Trigger" tab, you can set the frequency in which the script runs.

In the "Action" tab, select the run_monitor.cmd script and start in "C:\DNS_Monitor\"  
<img width="449" height="497" alt="Image" src="https://github.com/user-attachments/assets/d2ae07e6-8482-4efb-9119-fed969196531" />  

You can keep the rest of the settings as is or change them to your liking, once done, click OK.

## Viewing Alerts
The malicious IP detections appear in Event Viewer -> Windows Logs -> Application  
Look for entries with: Source: DNS_Monitor and Event ID: 1001


