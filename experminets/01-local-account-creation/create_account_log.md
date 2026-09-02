
Date/time: 			1 Sep 2026, ~21:33
Action: 			Created a new local user account named inside_account through Windows Settings while logged in as vboxuser.
Expected result: 		Windows account creation activity should be collected by Wazuh Agent and generate an alert.
Observed Result: 		Windows Security Event ID 4720 "A user account was created" was collected by Wazuh. 

data.win.system.eventID : 	4720
data.win.system.message: 	"A user account was created.
Account Name:			vboxuser
Account Domain:			WINDOWS11
Logon ID:			0x44FC3
rule.level			8
rule.id:			60109
Attributes:
	SAM Account Name:	inside_account

rule.mitre.tactic:		Persistence	
rule.mitre.technique:		Account Manipulation

				Event identified the account "vboxuser" created the new user "inside_account".
				Rule level "8" and mapped it to account manipulation attack and tactic of persistence.

Result: 			Success, account creation was logged by Wazuh agent and correctly identified the new account as well as account used for creation
				Provided information for useful filtering, and potential further leads like the account logon/name