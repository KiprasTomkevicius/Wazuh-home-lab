Date/time: 				2 Sep 2026, ~18:55
Action: 				Generate failed logon attempts onto the "inside_account"
Expected result: 			After 10 attempts within 10 minutes the account should should be locked out and the expected result is a
					log being generated about the account being locked out

Observed Result: 			after 6th logon attempt windows forced delay before next attempt
					after another 5 tries the logon screen is put into anopther delay before presenting the message "The referenced account is currently locked out and may not be logged on to."
					2 types of logs were generated, they will be looked at together:
				

data.win.system.eventID : 		4740 and 4625(same as failed logon attempt)
					the reason 4625 is mentioned in medium severity, as oppsoed to low like previous experiment is due to the system identifying multiple attempts, therefore classifying
					this log as brute force attempt.

data.win.system.message: 		"A user account was locked out." & "An account failed to log on"

					###Note eventID 4740 (lockout log) does not contain the following:

		Logon Type:			2

		Account For Which Logon Failed:
					Security ID:		S-1-0-0
					Account Name:		inside_account
					Account Domain:		WINDOWS11
		Network Information:
					Workstation Name:	WINDOWS11
					Source Network Address:	127.0.0.1
					Source Port:		0
		
					###Note eventID 4740 (lockout log) does however contain:

		Account That Was Locked Out:
					Security ID:		S-1-5-21-4268055879-2565299617-812491912-1001
					Account Name:		inside_account

		Additional Information:
					Caller Computer Name:	WINDOWS11"
					
					###lockout log contains less information on the source address and port then the multiple failure log

rule.description:			"Multiple Windows Logon Failures" & "User account locked out (multiple login errors)"

rule.level				9 					User account locked out (multiple login errors)
					10 					for multiple windows logon failures

rule.id:				60115					User account locked out (multiple login errors)
					60204					multiple windows logon failures
				

rule.mitre.tactic:			Credential Access, Impact		User account locked out (multiple login errors)
					Credential Access			multiple windows logon failures

rule.mitre.technique:			Brute Force, Account Access Removal	User account locked out (multiple login errors)
					Brute Force				multiple windows logon failures

data.win.eventdata.targetUserName	inside_account

data.win.eventdata.logonType:		2					(only shown on multiple windows logon failures)
rule.frequency				8 					(only for multiple failure log)

timestamp:				Sep 2, 2026 @ 19:00:04.925 & 	Sep 2, 2026 @ 19:00:05.988


Result: 				The lockout event was successfully logged by wazuh agent it is logged as level 9, however a surprisingly useful and interesting log was "An account failed to log" ID 4625 (same as a regular logon failure)
					I will refer to it as the multiple failure log. Multiple failure log contained additional information for the attempt, the source address, port and frequency of previous logs. It is less aggressively flagged by mitre
					techniques and tactics, being listed as brute force and credential access as opposed to lockout log also containing Impact and account access removal. It could be overlooked due to sharing the same Windows event ID despite
					being classified as level 10.