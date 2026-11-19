**Enterprise SOC Project – Windows Security \& Network Audit Report**



Audit Date: 18 November 2026

Audit Type: Windows Security and Network Configuration Review

Status: Practical Completed



**1. Windows Security Event Log Review**



Reviewed Windows Security logs for the following Event IDs:



Event ID| Description| Observation

4624| Successful Logon| Observed

4625| Failed Logon| Not observed in available filtered logs

4634| Account Logoff| Observed

4672| Special Privileges Assigned| Observed



**2. Windows Firewall Audit**



Reviewed all three firewall profiles:



\- Domain: Enabled

\- Private: Enabled

\- Public: Enabled



Observation: LogAllowed and LogBlocked were both disabled for all three profiles.



Recommendation: Review firewall logging requirements and enable appropriate logging according to organizational security policy.



**3. Network Ports Audit**



Reviewed listening TCP ports:



Port| Service / Purpose

80| HTTP

135| Windows RPC

445| SMB

3389| Remote Desktop

8080| Application/service port – requires verification

8082| Application/service port – requires verification

8083| Application/service port – requires verification



These ports are not automatically malicious. Their exposure and business requirement should be reviewed.



**4. Remote Desktop Services Audit**



\- Service Name: TermService

\- Display Name: Remote Desktop Services

\- Status: Running

\- Startup Type: Manual

\- Process ID: 1204

\- Listening Port: 3389



Observation: RDP was listening on all IPv4 interfaces.



Recommendation: Verify that RDP access is restricted to authorized users and trusted networks.



**5. Evidence Collected**



Screenshots were captured for:



\- Filtered Windows Security Events

\- Successful Login – Event ID 4624

\- Account Logoff – Event ID 4634

\- Special Privileges – Event ID 4672

\- Windows Firewall Audit – 2 screenshots

\- Windows Network Ports Audit

\- Windows RDP Service Audit



Evidence folder: "02-Windows-Security-Logs"



**6. Conclusion**



The practical reviewed Windows Security Events, Firewall Profiles, Listening TCP Ports, and Remote Desktop Services.



No failed logon event (4625) was observed in the available filtered logs. This does not establish that failed logons never occurred.



No configuration changes were made during this audit.



**Project:** Enterprise SOC Cybersecurity Learning Project

**Report Status:** Initial Audit Completed

