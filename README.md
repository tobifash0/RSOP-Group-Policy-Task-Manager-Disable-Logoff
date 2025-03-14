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

<br>

![Screenshot 2025-03-14 at 1 20 18 AM](https://github.com/user-attachments/assets/e834b551-6917-49b0-9880-ced1677a0151)

<br>

1. Next, right-click on Group Policy Objects and select New. Name the new policy "Task Manager". After creating it, select the Task Manager policy under Group Policy Objects. Then, go to the Delegations tab and select Add. 

![Screenshot 2025-03-14 at 1 24 51 AM](https://github.com/user-attachments/assets/d4e6d1ef-6db5-4891-acc3-4693cb6f3621)

<br> 

2. Add Bob to grant him the necessary permissions for this policy.
<br>

![image](https://github.com/user-attachments/assets/71ce1c15-00fb-4564-b98c-25912915b4fd)

<br> 
3. Right-click on Task Manager, select Edit, then go to User Configuration → Administrative Templates → System. Next, select Ctrl+Alt+Del Options.

<br> 
4. Here we will enable “Remove Change Password” and “Remove Task Manager”

<br> 

![image](https://github.com/user-attachments/assets/f7006c34-b9b6-4798-93c6-cfdb1e720155)

<br> 

5. Then back on the Group Policy Management, grab the “Task Manager” and move it to “HR”. Select “Yes”

<br> 

![Screenshot 2025-03-14 at 1 29 42 AM](https://github.com/user-attachments/assets/cb20a35a-a961-43c5-bb7f-665757ae5154)

<br> 

6. Select “Enforced” by right-clicking on it.

<br> 

<img width="621" alt="Screenshot 2025-03-14 at 1 49 41 AM" src="https://github.com/user-attachments/assets/f2fe4a20-0c1f-4ae3-9da6-6fc12dd466e9" />

<br>

7. Now, on Bob's account on Desktop2, open CMD and type the command gpupdate /force. This will immediately refresh the Group Policy settings for both the computer and user accounts.

<br> 


![image](https://github.com/user-attachments/assets/306605ac-87b4-4c3a-9a5d-d97f407c083b)

<br> 

8. After updating the Group Policy on Bob's computer, right-click on the taskbar, and you'll see that Task Manager is now greyed out, indicating that access has been successfully disabled.

<br> 

![image](https://github.com/user-attachments/assets/8d7cc73e-327e-4f99-b585-2356a89f3e24)

<br>

9. If we press Ctrl+Alt+Del on the virtual machine, we will see that the Change Password option has been removed, reflecting the changes made through Group Policy.

<br> 

![image](https://github.com/user-attachments/assets/740c3b89-36fb-4014-a6a8-607a58d4c67b)

<br> 

10. To check which group policies have been applied to Bob's computer, open the command line and type gpresult /r. This will display the results of the Group Policy settings for both the computer and user accounts.

<br> 

![Screenshot 2025-03-14 at 1 35 31 AM](https://github.com/user-attachments/assets/8134360b-76c4-4c79-a152-8b69d9894286)

<br> 

11. If you type taskmgr in the command line, a prompt will appear stating that Task Manager is disabled, confirming that the Group Policy to disable Task Manager has been successfully applied.

<br> 

![Screenshot 2025-03-14 at 1 35 59 AM](https://github.com/user-attachments/assets/006aa66f-8d9d-4af7-a147-b16d8249f88a)

<br> 

12. If you run Command Prompt as Administrator and then type taskmgr, Task Manager should open, as administrative privileges can bypass the policy restrictions applied to regular users.

<br> 

![image](https://github.com/user-attachments/assets/1ce005c3-9c21-4690-8c14-d34465bd63a6)

<br> 

13. To generate a Group Policy report, go to Group Policy Management, right-click on Group Policy Results, and select Group Policy Results Wizard.... This will guide you through the process of generating a detailed report on the applied Group Policy settings.


<br> 

![Screenshot 2025-03-14 at 1 39 02 AM](https://github.com/user-attachments/assets/9a73b7de-30b9-4c68-a076-7963f063ca7a)

<br> 

14. Click Next, then select Another Computer and click Browse. Type in Desktop2 and select it, then click Next to proceed with generating the Group Policy report for that computer.

<br> 

![Screenshot 2025-03-14 at 1 39 59 AM](https://github.com/user-attachments/assets/a84237c7-4cff-4109-922d-56c531e158dc)

<br> 

15. Select SimoTech\Bob, click Next, and then click Finish. This will generate a report for Bob's Group Policy settings.

<br>

![Screenshot 2025-03-14 at 1 42 23 AM](https://github.com/user-attachments/assets/b95f18c6-2901-46f8-be85-1bedf04a3ddc)

<br> 

16. If you select the Details tab at the top of the report, it will display all of the policies that have been applied to Bob's account, giving you a detailed view of the Group Policy settings.

<br>

![Screenshot 2025-03-14 at 1 43 15 AM](https://github.com/user-attachments/assets/7f424ad3-aa0c-4ecd-ab29-7459b8ce994c)

<br> 

17. Congratulations! We have successfully leveraged RSOP commands, explored Group Policy settings, utilized Task Manager, disabled logoff functionality, removed the ability to change passwords, and restricted access to Task Manager.

👉 [Next Lab 10 : Installing and Deploying Software with PDQ](https://github.com/tobifash0/Installing-and-Deploying-Software-with-PDQ)
