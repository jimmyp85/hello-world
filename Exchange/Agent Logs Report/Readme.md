# Exchange Server 2010: Agent Log Reports Script

This script has been written to run as a scheduled task and email the last 48 hours Agent Logs to a specified address.

## Parameters
The following Parameters should be set:

            Date: This has been set to get the last 48 hours from the date the script is run.
            Email To: Change this address to the person who is receiving the report
            Email From: Change to the address the report is being sent from
            Email Subject: This is set to include the date the report is generated
            SMTP Server: Change to your SMTP server IP address or host name
            Report File Name: Change this to the location and name of the report file created.

## Loading Exchange Snapin
This script has been written to run off a PC with Exchange management tools installed and so has a section to load the Exchange 2010 PowerShell snapin


## Agent Log Mapped Drive
The Get-AgentLogs command doesn't allow the use of a network path in a Location parameter so to get around this Agent Logs default location is mapped to drive Z: and the command run on this location. THis should be changed to the location of your agent logs.
