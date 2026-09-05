Date/time: 			5 Sep 2026, ~19:43
Action: 			Change the permissions of a local account giving it admin privilages
Expected result: 		A reletively high level log should be generated warning about an account being added as admin
Observed Result: 		Wazuh generated a high-severity log of level 12

data.win.system.eventID : 	4732
data.win.system.message: 	"A member was added to a security-enabled local group."

	"A member was added to a security-enabled local group.

	Subject:
		Security ID:		S-1-5-21-4268055879-2565299617-812491912-1000
		Account Name:		vboxuser
		Account Domain:		WINDOWS11
		Logon ID:		0x44D59

	Member:
		Security ID:		S-1-5-21-4268055879-2565299617-812491912-1001
		Account Name:		-

	Group:
		Security ID:		S-1-5-32-544
		Group Name:		Administrators
		Group Domain:		Builtin

	Additional Information:
		Privileges:		-"
'''
###indicates that no specific privileges were listed in this field; the privilege change is represented by the account being added to the Administrators group.
'''
data.win.eventdata.memberSid:	S-1-5-21-4268055879-2565299617-812491912-1001
'''
###the memberSid ending in 1001 belongs to inside_account, The account name isnt however listed on this log

rule.description:		Administrators Group Changed

rule.level			12
rule.id:			60154

rule.mitre.tactic:		Defense Evasion, Privilege Escalation
rule.mitre.technique:		Domain Policy Modification

timestamp:			Sep 5, 2026 @ 19:50:30.874


Result: 			The wazuh agent succesfully detected the account being moved to administrators group and
				assigned the log as high-severity. The log identifies which account performed the change and identifies the id of account which aqcuired the new privilages