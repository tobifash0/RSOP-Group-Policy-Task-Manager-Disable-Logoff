# Overview: Lab 9 RSOP, Group Policy, Task Manager, and Disable Logoff
This section of my home lab documentation focuses on configuring Group Policy, using RSOP (Resultant Set of Policy), managing Task Manager settings, and implementing a configuration to disable logoff in a Windows environment. The project demonstrates how to enforce specific policies across machines in a domain, monitor the effective policies using RSOP reports, and control system settings like logoff behavior and Task Manager access.

## Objectives

1. RSOP (Resultant Set of Policy): Use RSOP to generate reports on the effective policies applied to computers and users.
2. Group Policy Configuration: Create and configure Group Policies to enforce specific settings across domain-joined computers, including logoff policies and Task Manager access.
3. Task Manager Management: Customize Task Manager settings to control access, visibility, and processes for users in the domain.
4. Disable Logoff: Configure policies to disable logoff on domain-joined machines, ensuring users remain logged in for administrative purposes.
5. Policy Troubleshooting: Troubleshoot and resolve policy application issues using RSOP and Group Policy tools.

## Documentation
In this home lab, we will use RSOP commands, Group Policy Management, Task Manager, and disable logoff functionality. First, let's start by disabling Task Manager.

To do this, open Server Manager on your Windows Server 2022 account. Then, select Tools and click on Group Policy Management. In the Group Policy Management console, select Group Policy Objects under the SimoTech.com domain. From here, we can configure the Group Policy to disable Task Manager.

