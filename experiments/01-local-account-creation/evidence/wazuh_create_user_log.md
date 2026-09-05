{
  "_index": "wazuh-alerts-4.x-2026.09.01",
  "_id": "xiitXqABUlU9QSLCLG9h",
  "_score": 1,
  "_source": {
    "agent": {
      "ip": "192.168.56.108",
      "name": "SOC-Windows11",
      "id": "001"
    },
    "manager": {
      "name": "wazuh-server"
    },
    "data": {
      "win": {
        "eventdata": {
          "subjectLogonId": "0x44fc3",
          "scriptPath": "%%1793",
          "passwordLastSet": "%%1794",
          "homeDirectory": "%%1793",
          "userParameters": "%%1793",
          "subjectDomainName": "WINDOWS11",
          "displayName": "%%1793",
          "accountExpires": "%%1794",
          "homePath": "%%1793",
          "samAccountName": "inside_account",
          "targetUserName": "inside_account",
          "subjectUserSid": "S-1-5-21-4268055879-2565299617-812491912-1000",
          "primaryGroupId": "513",
          "logonHours": "%%1797",
          "targetDomainName": "WINDOWS11",
          "profilePath": "%%1793",
          "userWorkstations": "%%1793",
          "oldUacValue": "0x0",
          "newUacValue": "0x15",
          "targetSid": "S-1-5-21-4268055879-2565299617-812491912-1001",
          "userAccountControl": "    %%2080    %%2082    %%2084",
          "subjectUserName": "vboxuser"
        },
        "system": {
          "eventID": "4720",
          "keywords": "0x8020000000000000",
          "providerGuid": "{54849625-5478-4994-a5ba-3e3b0328c30d}",
          "level": "0",
          "channel": "Security",
          "opcode": "0",
          "message": "\"A user account was created.\r\n\r\nSubject:\r\n\tSecurity ID:\t\tS-1-5-21-4268055879-2565299617-812491912-1000\r\n\tAccount Name:\t\tvboxuser\r\n\tAccount Domain:\t\tWINDOWS11\r\n\tLogon ID:\t\t0x44FC3\r\n\r\nNew Account:\r\n\tSecurity ID:\t\tS-1-5-21-4268055879-2565299617-812491912-1001\r\n\tAccount Name:\t\tinside_account\r\n\tAccount Domain:\t\tWINDOWS11\r\n\r\nAttributes:\r\n\tSAM Account Name:\tinside_account\r\n\tDisplay Name:\t\t<value not set>\r\n\tUser Principal Name:\t-\r\n\tHome Directory:\t\t<value not set>\r\n\tHome Drive:\t\t<value not set>\r\n\tScript Path:\t\t<value not set>\r\n\tProfile Path:\t\t<value not set>\r\n\tUser Workstations:\t<value not set>\r\n\tPassword Last Set:\t<never>\r\n\tAccount Expires:\t\t<never>\r\n\tPrimary Group ID:\t513\r\n\tAllowed To Delegate To:\t-\r\n\tOld UAC Value:\t\t0x0\r\n\tNew UAC Value:\t\t0x15\r\n\tUser Account Control:\t\r\n\t\tAccount Disabled\r\n\t\t'Password Not Required' - Enabled\r\n\t\t'Normal Account' - Enabled\r\n\tUser Parameters:\t<value not set>\r\n\tSID History:\t\t-\r\n\tLogon Hours:\t\tAll\r\n\r\nAdditional Information:\r\n\tPrivileges\t\t-\"",
          "version": "0",
          "systemTime": "2026-09-01T20:33:17.8243989Z",
          "eventRecordID": "11954",
          "threadID": "904",
          "computer": "windows11",
          "task": "13824",
          "processID": "796",
          "severityValue": "AUDIT_SUCCESS",
          "providerName": "Microsoft-Windows-Security-Auditing"
        }
      }
    },
    "rule": {
      "mail": false,
      "level": 8,
      "pci_dss": [
        "8.1.2",
        "10.2.5"
      ],
      "hipaa": [
        "164.312.a.2.I",
        "164.312.a.2.II",
        "164.312.b"
      ],
      "tsc": [
        "CC6.8",
        "CC7.2",
        "CC7.3"
      ],
      "description": "User account enabled or created",
      "groups": [
        "windows",
        "windows_security",
        "adduser",
        "account_changed"
      ],
      "nist_800_53": [
        "AC.2",
        "IA.4",
        "AU.14",
        "AC.7"
      ],
      "gdpr": [
        "IV_35.7.d",
        "IV_32.2"
      ],
      "firedtimes": 1,
      "mitre": {
        "technique": [
          "Account Manipulation"
        ],
        "id": [
          "T1098"
        ],
        "tactic": [
          "Persistence"
        ]
      },
      "id": "60109",
      "gpg13": [
        "7.10"
      ]
    },
    "decoder": {
      "name": "windows_eventchannel"
    },
    "input": {
      "type": "log"
    },
    "@timestamp": "2026-09-01T20:33:20.439Z",
    "location": "EventChannel",
    "id": "1788294800.262826",
    "timestamp": "2026-09-01T20:33:20.439+0000"
  },
  "fields": {
    "timestamp": [
      "2026-09-01T20:33:20.439Z"
    ],
    "@timestamp": [
      "2026-09-01T20:33:20.439Z"
    ]
  }
}