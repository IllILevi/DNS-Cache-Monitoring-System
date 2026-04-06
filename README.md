# DNS-Cache-Monitoring-System
This is a windows OS-level DNS cache monitoring system that runs a PowerShell script to access your DNS cache, calls the Virus Total API to check each unique DNS for malware.


## Setup Instructions
### 1. Save PowerShell script to directory.
recommended file path: C:\DNS_Monitor\
Then save the CMD script to that folder.
C:\DNS_Monitor\check_dns.cmd

### 2. Create the scheduled task.
There are two options to do this step: either through the command line interface or through the Windows Task Scheduler GUI. Instructions for both methods will be shown below.

#### Option A: Using Command Line
Run the command prompt as administrator and enter the following command:

schtasks /create /tn "DNSCacheMonitor" /tr "C:\DNS_Monitor\check_dns.cmd" /sc hour /mo 1 /ru SYSTEM

