# CheckDCPorts.ps1
A script to check Active Directory Domain Services required ports

# Examples:

- Check fort open/closed ports for every DC in the domain

  > .\CheckDCPorts.ps1 -Domain contoso.com

- Check for Latency only to every DC in the domain

  > .\CheckDCPorts.ps1 -LatencyOnly -Domain contoso.com

- Check only against a particular server or servers

  > .\CheckDCPorts.ps1 -Server DC1.contoso.com

  > .\CheckDCPorts.ps1 -Server DC1.contoso.com,DC2.contoso.com
  
  > .\CheckDCPorts.ps1 -Server DC1.contoso.com,DC2.contoso.com -LatencyOnly

# Notes:
- Run it on a DC to check DC to DC communication, or a server/client to check Client to DC communication.

- The -Domain parameter requires the PowerShell AD module to be installed -part of AD RSAT (activedirectory)

- Ports checked are:
	-   88	  Kerberos
	-   389	  LDAP
	-   636	  LDAPS
	-   445	  SMB
	-   3268	Global Catalog LDAP
	-   3269	Global Catalog LDAPs
	-   139   NetBIOS SSN	  
  -   464   Kerberos Password Change
	-   5722  WS 2008 R2 and below DFSR
	-   9389  PowerShell GET-AD* CmdLets
	-   5985  PowerShell Remoting
	-   5986  PowerShell Remoting over SSL
	-   123	  NTP
	-   53    DNS
	
# Sample Screenshot
![](https://github.com/luisfeliz79/CheckDCPorts.ps1/raw/master/SampleOutput.PNG)
