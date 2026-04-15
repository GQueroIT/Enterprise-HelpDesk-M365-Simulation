# Jira Ticket Lifecycle Notes

## Overview

This section documents the initial Jira Service Management setup completed for the Enterprise Help Desk & Microsoft 365 Simulation project. The goal of this phase was to bring the help desk ticketing system online and use it to simulate a realistic IT support incident tied directly to the existing Active Directory environment.

The Jira environment was created as the primary ticketing platform for the lab. After setup, a real support scenario was simulated involving a user who could not access a mapped network drive connected to the HR shared folder.

---

## Objectives

- Deploy Jira Service Management as the primary ticketing platform
- Create a realistic help desk ticket tied to the existing lab environment
- Simulate a file share access issue
- Investigate the issue as a help desk analyst
- Resolve the issue and document the full ticket lifecycle

---

## Jira Setup Summary

The Jira Service Management environment was configured using the IT support and service request options during setup. A basic IT service management space was selected in order to quickly establish a functional help desk workflow without building the environment from scratch.

The help desk space was created with the following details:

- Space Name: SmarTech Help Desk
- Team Type: IT team
- Access Model: Open
- Platform Used: Jira Service Management Cloud

This established the main service desk environment that will be used for future incidents, requests, and troubleshooting workflows throughout the project.

---

## Ticket Scenario Created

The first incident created in Jira was based on an issue from the Active Directory lab environment.

### Ticket Summary
User unable to access mapped network drive (Z:)

### Environment Context
- Domain: corp.smartech.com
- Workstation: WORKSTATION01
- Shared Folder: HR-Shared
- Share Path: C:\Shares\HR-Shared

The ticket simulated a user being able to see the mapped drive but receiving an access denied error when attempting to open it.

---

## Simulated Issue

To make the ticket realistic, access permissions were intentionally removed from the affected user. This created a real access failure rather than only documenting a hypothetical issue.

The issue was reproduced successfully on the workstation, confirming that the mapped drive was visible but inaccessible.

This was important because it demonstrated the full workflow of a real support case:
- ticket intake
- issue reproduction
- investigation
- resolution
- validation
- ticket closure

---

## Investigation Summary

The investigation confirmed that:
- the user could authenticate successfully to the domain
- Group Policy drive mapping was still functioning
- the mapped drive was visible
- the actual issue was related to missing NTFS permissions on the HR-Shared folder

This narrowed the root cause to file share access permissions rather than authentication, network connectivity, or Group Policy failure.

---

## Resolution Summary

Access was restored by adding the affected user back to the appropriate permissions on the HR-Shared folder.

After permissions were restored:
- the mapped drive opened successfully
- the user could access the shared folder
- the issue was considered resolved
- the Jira ticket was updated and closed

---

## Outcome

This phase successfully demonstrated the use of Jira Service Management within the help desk simulation project. It also established a repeatable workflow for future incidents involving account access, file shares, Group Policy, login failures, and other common IT support scenarios.

This ticket serves as the first complete incident lifecycle example in the project and connects the ticketing platform directly to the Active Directory environment already built in the earlier phase.