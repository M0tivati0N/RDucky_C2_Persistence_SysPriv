RDucky_C2_Session_with_System_Privileges_Persistence


This script for Rubber Ducky will:

1> Open an Admin Powershell session from Run window
Deactivate firewall and Windefend (at startup too), and delete Run Hystory
Download and run an amazing tool 'RunAsTI' by jschicht https://github.com/jschicht/RunAsTI
Create a startup scheduled task which will download and run your payload
Clear logs

Notes:
Tested on Windows 10 Pro VM (WinDefender and no other AV)
You might want to edit DELAY times
Replace the schtask Server IP and Port number with those of your preference
Don't forget to obfuscate your payload (AV evasion)
Have your servers running and listening (for both payload delivery and C2)
Script needs to be reinitiated if RunAsTI does not open a cmd window at first attempt
RunAsTI allows for our scheduled task to be executed with very High Priviledges
Therefore, once Windows 10 is rebooted, a connection with your C2 server is established,
and a high integrity session/agent is created - with System Privileges (tested with Empire)
Windows will reactivate WinDefend at some point, with an update or similar
This method will bypass Defender and AMSI initially, but will be blocked sooner or later.
However, often WinDefender gets deactivated in presence of an AV
If this is the case, and your payload can bypass AVs, then problem won't exist.
