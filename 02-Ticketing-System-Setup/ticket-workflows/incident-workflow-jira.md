# Incident Workflow - Jira Service Management

## Purpose

This document outlines the workflow used to handle incidents within the Jira Service Management environment for the Enterprise Help Desk & Microsoft 365 Simulation project.

The purpose of this workflow is to reflect a realistic help desk process that can be repeated across future support cases.

---

## Workflow Stages

### 1. Ticket Intake

The process begins when a user submits or reports an issue. The ticket is created in Jira with a clear summary, description, and business impact.

For this project, the first incident involved a user being unable to access the mapped Z: drive.

Key intake details should include:
- affected user
- affected device
- symptoms reported
- impact on work
- time issue began if known

---

### 2. Initial Review

Once the ticket is received, the issue is reviewed to determine the likely area of failure. This stage focuses on understanding whether the issue may be related to user authentication, permissions, network connectivity, policy application, software behavior, or system access.

At this point, the ticket remains open and active while initial observations are documented.

---

### 3. Issue Reproduction

The next step is to verify that the issue can actually be reproduced. This is important because support decisions should be based on confirmed behavior rather than assumptions alone.

In this case, the issue was reproduced by logging into the workstation and attempting to open the mapped Z: drive, which returned an access denied error.

---

### 4. Investigation

During the investigation phase, the environment is reviewed to isolate the root cause.

Examples of investigative actions include:
- checking domain sign-in status
- confirming device and user state
- verifying drive mapping
- reviewing Active Directory configuration
- checking share and NTFS permissions
- testing connectivity where applicable

For this case, the investigation confirmed that the user could authenticate successfully and the drive was mapped correctly, but the user lacked required NTFS permissions on the HR-Shared folder.

---

### 5. Documentation During Work

Throughout the investigation, updates are added to the ticket in Jira. These comments record:
- what has been tested
- what has been confirmed
- what the suspected cause is
- what the next step will be

This creates a clear support trail and makes the work understandable to another technician if escalation is needed.

---

### 6. Resolution

Once the root cause is confirmed, the issue is corrected using the least disruptive valid fix.

In this scenario, the missing permissions were restored on the HR-Shared folder so the user could regain access.

The resolution step should always be specific enough to explain what was changed.

---

### 7. Validation

After applying the fix, the issue must be tested again. Validation confirms that the change actually solved the problem and that the user can perform the required task successfully.

For this case, validation confirmed that:
- the mapped drive was accessible
- the folder opened successfully
- the issue no longer occurred

---

### 8. Customer Communication

Before closing the ticket, a resolution update is provided. This explains in clear language that the issue has been fixed and asks the user to confirm normal operation if appropriate.

This step is important because technical fixes alone are not enough. Communication is part of the support process.

---

### 9. Ticket Closure

Once the issue is resolved and validated, the ticket is moved to a completed state such as Done or Resolved.

The closure should reflect:
- what the issue was
- what caused it
- what was done to fix it
- confirmation that the issue was no longer present

---

## Workflow Value

This workflow helps ensure that incidents are handled consistently and professionally. It also creates a repeatable support structure that can be applied to future scenarios such as:

- password reset requests
- account lockout incidents
- mapped drive failures
- Group Policy issues
- DNS and connectivity problems
- Microsoft 365 access issues

---

## Summary

The Jira incident workflow used in this project follows a realistic support pattern:

1. Intake
2. Review
3. Reproduction
4. Investigation
5. Documentation
6. Resolution
7. Validation
8. Communication
9. Closure

This workflow forms the foundation for the ticket handling process used throughout the Enterprise Help Desk & Microsoft 365 Simulation project.