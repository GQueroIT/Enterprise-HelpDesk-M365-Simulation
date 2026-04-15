# Troubleshooting Case - User Unable to Access Mapped Network Drive

## Incident Summary

A user reported being unable to access the mapped network drive (Z:) from a domain-joined workstation. The drive was visible in File Explorer, but the user received an access denied error when attempting to open it.

This issue was tracked through Jira Service Management as part of the Enterprise Help Desk & Microsoft 365 Simulation project.

---

## Environment

- Domain: corp.smartech.com
- Domain Controller: DC01
- Workstation: WORKSTATION01
- Shared Folder: HR-Shared
- Local Share Path: C:\Shares\HR-Shared
- Ticketing Platform: Jira Service Management

---

## Reported Symptoms

- User could sign in successfully to the workstation
- Mapped drive (Z:) appeared in File Explorer
- Access to the folder failed with an access denied message
- User could not open files required for normal work

---

## Initial Hypothesis

At the beginning of the investigation, several possible causes were considered:

- domain login issue
- Group Policy mapping issue
- network connectivity problem
- share permission problem
- NTFS permission issue

Because the drive was visible, the issue was less likely to be related to Group Policy mapping and more likely related to access permissions on the shared resource.

---

## Troubleshooting Steps Performed

### 1. Verified user sign-in
The affected user was able to authenticate successfully to the domain on WORKSTATION01.

### 2. Verified mapped drive presence
The Z: drive was present in File Explorer, confirming that Group Policy drive mapping was still applying successfully.

### 3. Reproduced the issue
An attempt was made to open the mapped drive from the workstation. The access denied message confirmed the issue was active and reproducible.

### 4. Reviewed share location
On DC01, the HR-Shared folder was confirmed to exist under the expected path:
`C:\Shares\HR-Shared`

### 5. Reviewed folder permissions
The Security tab on the HR-Shared folder was reviewed. The affected user no longer had the required NTFS permissions to access the folder.

---

## Root Cause

The root cause of the issue was missing NTFS permissions on the HR-Shared folder for the affected user.

The user account was still valid in Active Directory, and the drive mapping itself was still functioning. The failure occurred because the user no longer had sufficient permissions to open the folder contents.

---

## Resolution

The affected user was added back to the correct permissions on the HR-Shared folder.

After permissions were restored:
- access to the mapped drive was tested again
- the user was able to open the shared folder successfully
- the incident was marked resolved in Jira

---

## Validation

The fix was validated by confirming the following:

- the user could still sign in normally
- the mapped drive remained visible
- the mapped drive opened without error
- the user could access the shared folder contents successfully

---

## Final Result

The issue was resolved successfully by restoring the required NTFS permissions to the affected user.

This case demonstrated a realistic help desk workflow involving:
- ticket creation
- issue simulation
- problem reproduction
- permissions investigation
- access restoration
- validation
- ticket closure

---

## Lessons Learned

This case reinforced that a mapped drive being visible does not automatically mean the user has access to the underlying folder. It is possible for drive mapping to succeed while NTFS permissions still prevent access.

This scenario also showed the importance of separating:
- authentication issues
- Group Policy mapping issues
- network path issues
- file system permission issues

That distinction is critical in real-world help desk troubleshooting.