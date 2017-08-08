# NetConfigBackup
Created by user Code Brock
This application will be connect to a switch and issue a command to backup the running configuration of the switch on to a TFTP server.
This application can be used to connect to a single switch or used in conjunction with a specified XML file to connect to multiple switches.


Files:
NetConfigBackup.py - Call this file to run the backup with supplied parameters
    -x --xml <Path to XML File>    For use in specifying an XML file of switches, good for large number of switches

    For using on a single switch
    -i --IP     Switch IP Address or hostname.
    -u --login-username <USER> Username used to log into the switch.
    -p --login-password <PASSWORD> Password used to log into the switch.
    -e --enable-password <ENABLE PASSWORD>
    -d --driver specify the driver and connection to be used.
        Available drivers are <populate from  drivers directory>
    -a --tftp server address in relation to the switch being connected from.
    -h --help Display help and list of applicable drivers.
    Usage examples:
         NetConfigBackup.py -x swicthes.xml
         NetConfigBackup.py -i 192.168.1.200 -p P@ssw0rd -e En@bled -d BrocadeTelnet
Switches.xml - XML file containing settings for multiple switches
<?xml version="1.0"?>
<switches>
	<switch name="SW1">
		<ip>192.168.1.200</ip>
		<login>user</login>
		<password>********</password>
		<enable>*******</enable>
		<driver>CiscoTelnet</driver>
		<tftp>192.168.1.100</tftp>
	</switch>
<switches>

