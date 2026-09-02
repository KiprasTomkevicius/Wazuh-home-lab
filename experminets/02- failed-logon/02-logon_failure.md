
Date/time: 			2 Sep 2026, ~13:47
Action: 			Attempted windows login with correct and incorrect credentials.
Expected result: 		Logon attempt to be logged by wazuh agent, generating logs for failed attempts
Observed Result: 		

data.win.system.eventID : 	4625
data.win.system.message: 	Account For Which Logon Failed:
				Security ID:		S-1-0-0
				Account Name:		inside_account
				Account Domain:		WINDOWS11

	Failure Information:
				Failure Reason:		Unknown user name or bad password.

	Network Information:
				Workstation Name:	WINDOWS11
				Source Network Address:	127.0.0.1
				Source Port:		0

rule.description:		Logon Failure - Unknown user or bad password

rule.level			5
rule.id:			60122

rule.mitre.tactic:		Impact	
rule.mitre.technique:		Account Access Removal

rule.firedtimes:		4
data.win.eventdata.logonType:	2

timestamp:			Sep 2, 2026 @ 14:01:28.602

				Event identified a local failed attempt was made to log onto "inside_account" account. Wazuh agent identified it
				as a level 5 rule putting logs about this in "low threat".
				Wazuh agent identified this attempt as "account access removal" with the tactic of "Impact"
				Wazuh agent identified this this rule as having been triggered 4 times
				The log identifies failure reason as "unknown username or bad password"

Result: 			Overall succesful, there were logs made for attempted log on attempts. The information from logs tells a lot of information
				about said attempts. The attempts were put at level 5 meaning they were counted as low risk, the temporary slow down to
				log on attempts didnt generate a medium threat log either.