Date/time: 			7 Sep 2026, ~18:43
Action: 			Create a file, on local account and remove access from it and only leave administrator group access to it. then attempt to access the file
Expected result: 		File access while not using administrator should be denied, and a log about denial should be generated
Observed Result: 		Initially, the file access was denied however no logs were generated. NTFS permission enforcement does not automatically audit access.
				
				Changes to Windows auditing settings were made to enable logging of failed file access attempts:
				administrator command prompt:
				auditpol /set /subcategory:"File System" /success:enable /failure:enable
				auditpol /get /subcategory:"File System"

The rule change generated windows security logs:

eventID:			4719
description:			"Windows Audit Policy changed"
category:			Object Access
subcategory:			File System
auditPolicyChanges:		Success added
Wazuh rule:			60112

rule level:			8
'''
###Changing the Windows File System audit policy generated a Security event which was successfully collected by Wazuh. Event ID 4719 was identified as "Windows Audit Policy changed" and was classified by Wazuh as rule level 8.

Windows File System auditing was enabled for Success and Failure and an auditing entry was added to only_for_admin.txt. Successful access-related events for the file were generated as Event ID 4663.
However, when inside_account attempted to access the file at approximately 19:39:25 and received "Access is denied", no corresponding 4656 failure event was generated in the Windows Security log.
Because Windows did not generate a corresponding failure audit event for the denied access attempt, there was no event for the Wazuh agent to ingest or alert on.
'''
