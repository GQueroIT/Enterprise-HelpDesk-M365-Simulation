## Step 05 — Organizational Units and User Creation

Created a structured OU hierarchy to simulate an enterprise environment:

- IT
- HR
- Workstations
- Servers
- Service Accounts

Created standard user accounts:

- Angelina Greyhand (agreyhand)
- Lilly Fierce (lfierce)

Created administrative account:

- IT Admin (itadmin)

Assigned privileges:

- Added itadmin to the Domain Admins group

Verification:

- Used `Get-ADUser itadmin` to verify successful admin account creation
- Used `Get-ADGroupMember "Domain Admins"` to verify domain admin group membership

## Key Takeaways

- Organizational Units provide logical structure for administrative management
- Standard user accounts should remain separate from privileged admin accounts
- Small command typos can cause failures, so error messages must be read carefully during troubleshooting
- Role-based access control improves security and accountability

## Real-World Relevance

In enterprise environments, OU design helps organize users, systems, and policy application. Dedicated administrative accounts are a security best practice because they separate elevated privileges from day-to-day user activity and improve control over access management.