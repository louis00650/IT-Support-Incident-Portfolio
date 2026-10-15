# IT Support Troubleshooting Lab

I use a VMware home lab to practise everyday Windows and helpdesk issues: reproducing a problem, checking the likely causes, making a targeted fix, and testing again as the affected user.

The lab runs Windows Server 2025 (Active Directory and DNS) and a domain-joined Windows 11 client on a Host-only virtual network. 

## Incident notes

| Case | Issue | What I tested | Result |
| --- | --- | --- | --- |
| [INC-001](incidents/INC-001-disabled-account/README.md) | Domain sign-in denied | DC discovery, LDAP connectivity, AD account state, Kerberos | Resolved |
| [INC-002](incidents/INC-002-account-lockout/README.md) | Account locked after failed sign-ins | Fine-Grained Password Policy, Event 4740, AD account unlock, Kerberos | Resolved |
| [INC-003](incidents/INC-003-password-change/README.md) | Password change required at sign-in | AD password reset, pwdLastSet, password policy, Kerberos | Resolved |
| [INC-004](incidents/INC-004-department-transfer/README.md) | Department transfer — access denied | AD Groups, SMB, NTFS, Security Tokens | Resolved |
| [INC-005](incidents/INC-005-temporary-windows-profile/README.md) | Temporary Windows profile after sign-in | User Profile Service, NTUSER.DAT, Event Viewer | Resolved |
| [INC-006](incidents/INC-006-wrong-account-context/README.md) | Wrong Account Context — Local vs Domain Sign-in | Local SAM, Active Directory, authentication context, SIDs | **Verified** |
| [INC-007](incidents/INC-007-hr-share-access-denied/README.md) | Access Denied to HR Shared Folder | AD Groups, SMB Share Permissions, NTFS ACLs | **Verified** |
| [INC-008](incidents/INC-008-read-only-share-write-denied/README.md) | Can Read Shared Files but Cannot Create Them | AD Groups, SMB Share Permissions, NTFS ACLs | **Verified** |
| [INC-009](incidents/INC-009-mapped-drive-missing/README.md) | Mapped Network Drive Missing After Sign-in | Group Policy scope, OU placement, Drive Maps, gpresult | Verified |
| [INC-010](incidents/INC-010-gpo-department-scope/README.md) | Desktop GPO Applies to IT but Not HR | Group Policy links, OU scope, gpresult | Verified |
| [INC-011](incidents/INC-011-software-deployment-gpo-scope/README.md) | Assigned Software Not Installing Through GPO | Computer OU scope, GPO Software Installation, MSI, gpresult | **Verified** |
| [INC-012](incidents/INC-012-roaming-profile-sync-failure/README.md) | Roaming Profile Not Updated on a Second Workstation | Roaming profiles, SMB connectivity, Windows Firewall, cached profile, cross-client verification | **Verified** |
| [INC-013](incidents/INC-013-incorrect-dns-ad-discovery/README.md) | Incorrect DNS Server Prevents AD Service Discovery | DNS configuration, SRV record lookup, IP connectivity, DC discovery, PowerShell diagnostics | Resolved |
| [INC-014](incidents/INC-014-incorrect-hosts-file-resolution/README.md) | Incorrect Hosts File Entry Causes Wrong Hostname Resolution | Windows hosts file, DNS name resolution, Resolve-DnsName, SMB troubleshooting | Resolved |
| [INC-015](incidents/INC-015-apipa-dhcp-lease-failure/README.md) | Client Receives an APIPA Address After DHCP Failure | DHCP, APIPA, ipconfig, VMware host-only networking, IPv4 troubleshooting | Resolved |
| [INC-016](incidents/INC-016-duplicate-ip-address-conflict/README.md) | Duplicate Static IP Address Causes Network Connectivity Failure | IPv4 conflict detection, Get-NetIPAddress, AddressState, APIPA, DHCP recovery | Resolved |





Each case includes the actual commands and screenshots from the lab. I'll add new cases as I finish and verify them.

*These are simulated incidents, not customer or workplace tickets.*
