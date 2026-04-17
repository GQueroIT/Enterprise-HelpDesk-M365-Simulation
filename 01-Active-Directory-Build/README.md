# Active Directory Build

This section documents the full build of an on-premises Active Directory environment designed to simulate a real enterprise setup. The goal was to create a structured domain, organize users and systems, and implement controlled access using proper delegation.

---

## Environment Overview

- Windows Server (Domain Controller)
- Domain: `corp.smartech.com`
- Organizational Units for departments (HR, IT, Servers, Workstations, etc.)
- Security groups for role-based access control
- Domain-joined workstation for testing

---

## Build Steps

### Step 01 – Network Setup
Configured static IP addressing and verified connectivity between systems.

### Step 02 – Server Identity
Renamed server and prepared it for domain controller promotion.

### Step 03 – Active Directory Installation
Installed AD DS and promoted the server to a domain controller.

### Step 04 – Domain Controller Configuration
Configured the new domain `corp.smartech.com` and validated services.

### Step 05 – Users and OUs
Created organizational units and structured users based on departments.

### Step 06 – Groups and Permissions
Created security groups and began implementing role-based access control.

### Step 07 – Workstation Setup
Configured client machine and prepared it for domain integration.

### Step 08 – Domain Join
Joined the workstation to the domain and verified connectivity.

### Step 09 – GPO Drive Mapping
Configured Group Policy to map network drives automatically.

### Step 10 – User Login and File Shares
Tested user logins and validated access to shared resources.

---

## Step 11 – Help Desk Delegation (Workstations OU)

In this step, I implemented delegation of control for the Help Desk role using the `IT_Admins` group.

The goal was to allow Help Desk to manage workstation computer objects without giving full Domain Admin privileges.

## Step 12 – Sales User Provisioning Automation

In this step, I expanded the Active Directory environment by automating the provisioning of additional Sales department users using PowerShell.

The goal was to create a scalable and realistic onboarding workflow that could support future help desk tickets, permissions scenarios, and group-based administration.

## What I configured:
- Created an interactive PowerShell automation script for employee provisioning
- Implemented dynamic input prompts for:
- First Name
- Last Name
- Display Name (auto-generated if not provided)
- Username (auto-generated if not provided)
- User Principal Name (auto-generated if not provided)
- Department
- Title
- Built department-based automation logic to eliminate manual OU and group selection:
- Sales → Sales OU + Sales_Team group
- HR → HR OU + HR_Team group
- IT → IT OU + IT_Admins group
- Added validation checks for:
- Existing users (prevents duplicates)
- OU existence
- Group existence
- Configured accounts with a standard lab password and non-expiring password policy
- Implemented structured CSV logging to track provisioning results including:
- Created (successful user creation)
- Skipped (user already exists)
- Error (invalid input, OU/group issues)

## Validation performed:
- Verified correct OU mapping based on department input
- Confirmed users were created in the correct Organizational Unit
- Validated automatic group membership assignment
- Tested duplicate user handling (Skipped status)
- Tested invalid input handling (Error status)
- Reviewed CSV log output for accuracy and consistency

## What I learned:
Automation significantly reduces manual configuration errors and speeds up onboarding workflows.

Abstracting infrastructure (OU and group mapping) allows administrators to work more efficiently without needing to remember full Distinguished Names.

Proper validation and logging are critical for real-world environments, ensuring accountability and simplifying troubleshooting.

Key takeaway:
Automation is not just about speed — it is about consistency, accuracy, and scalability. This approach mirrors how enterprise environments handle user provisioning through standardized workflows.

---

## Key Skills Demonstrated

- Active Directory Domain Services (AD DS) deployment  
- Organizational Unit (OU) design  
- Group-based access control  
- Group Policy configuration  
- Domain join and client configuration  
- File share and access validation  
- Delegation of control (least privilege model)  
- Troubleshooting access and permission issues  

---

## Evidence

All screenshots and supporting files are organized under:
01-Active-Directory-Build/evidence/


Each step includes corresponding documentation and validation.

---

## Outcome

Successfully built and configured a functional Active Directory environment with realistic structure and permissions.

Implemented a Help Desk delegation model that allows administrative tasks without over-privileging users, simulating real-world enterprise practices.
