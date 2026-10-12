# IT Support Troubleshooting Lab

I use a VMware home lab to practise everyday Windows and helpdesk issues: reproducing a problem, checking the likely causes, making a targeted fix, and testing again as the affected user.

The lab runs Windows Server 2025 (Active Directory and DNS) and a domain-joined Windows 11 client on a Host-only virtual network. 

## Incident notes

| Case | Issue | What I tested | Result |
| --- | --- | --- | --- |
| [INC-001](incidents/INC-001-disabled-account/README.md) | Domain sign-in denied | DC discovery, LDAP connectivity, AD account state, Kerberos | Resolved |

Each case includes the actual commands and screenshots from the lab. I'll add new cases as I finish and verify them.

*These are simulated incidents, not customer or workplace tickets.*
