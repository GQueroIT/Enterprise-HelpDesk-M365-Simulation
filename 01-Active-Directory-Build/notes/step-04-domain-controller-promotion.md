## Step 04 — Domain Controller Promotion (DC01)

Promoted DC01 to a Domain Controller and created a new Active Directory forest.

Domain Configuration:

- Domain Name: corp.smartech.com
- NetBIOS Name: SMARTECH
- DNS Installed: Yes

Command used:

- Install-ADDSForest with DNS and Safe Mode Administrator Password

Post-installation:

- Server automatically restarted
- Logged in using domain credentials: SMARTECH\Administrator

Verification:

- Confirmed domain membership using `whoami`
- Verified domain using `Get-ADDomain`

## Key Takeaways

- Promoting a server to a domain controller establishes centralized identity management
- DNS is required for Active Directory to function properly
- Proper domain naming improves scalability and realism in enterprise environments

## Real-World Relevance

In enterprise environments, domain controller promotion is a critical step that enables authentication, authorization, and centralized management of users and systems. DNS integration ensures proper service discovery and communication across the network.