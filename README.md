# Genexis-Password-Attack


A critical vulnerability has been identified in the configuration of Genexis modem/router devices, where the default admin password for accessing the device's configuration page is set to be the same as the device's MAC address. An attacker in the same network can retrieve the MAC address from the ARP cache and exploit this vulnerability.
Tested On Platinum-4410(P4410-V2-1.33)
Steps to reproduce this vulnerability.
1.	From your Genexis modem ensure that the MAC address and configuration page passwords are the same. This will ensure that you are using the vulnerable product.
2.	Open 192.168.1.1(This will change based on your IP address class) and ensure that the modem configuration page is accessible.
3.	Type arp -a <config page IP> and get the physical address. Remove ‘– ‘and convert the string to uppercase.
4.	You can also use the following exploit.py file for retrieving the password.
5.	Use this password for the user admin, if the modem is configured with default credentials, then you can access the configuration page.
Mitigation:

Immediate Password Change: 
1.	Genexis Modem Software must force the user to change the password during the initial configuration.
2.	Users should immediately change the default administrative password to a strong, unique passphrase that is not easily guessable or derived from any publicly available information such as the MAC address.
