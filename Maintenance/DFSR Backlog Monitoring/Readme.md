# DFSR Backlog Monitoring Script
version 1.0

## Purpose
This script is written to be run as a scheduled task on a file server running DFSR to send out showing any backlogs and the files affected.

## Parameters to Change
The following parameters need to be changed in the script:

##### $DFSroot
Change this to your DFS namespace
##### $smtpServer
Change this to the hostname or IP address of your SMTP server
##### $smtpFrom
Change this to the email address the report will be sent from
##### $smtpTo
Change this to the email address the report will be sent to.
##### $Subject (optional)
Optionally you can change the subject of the email that will be sent. 

## Scheduled Task Settings
The following settings should be set in Windows Task Scheduler.
##### General
- Should be run under and administrator account
- Run with highest privileges
- Run whether user is logged on or not

##### Triggers
Set this to run at the frequancy you desire. For example you could run this daily at 0800 every day.
##### Actions
- Action: Start a program
- Program/Script: %SystemRoot%\System32\WindowsPowerShell\v1.0\powershell.exe
- Add arguments: This should be the location the .ps1 file is saved in. For example: C:\Support\Scripts\dfsr_backlog.ps1

##### Conditions, Settings & History
These can be left at default or changes for your own needs.

##### Testing
Once you have set your sceduled task up run it to make sure it works

## Running the script
The script can be run from a PowerShell console as well as with a scheduled task. To do this change the console location to the location of your script.
```powershell
>cd C:\ScriptLocation
```
Then run the script with .\ like below.
```powershell
>.\dfsr_backlog.ps1
```
