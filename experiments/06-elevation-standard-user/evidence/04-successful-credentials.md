{
  "_index": "wazuh-alerts-4.x-2026.09.08",
  "_id": "P-2NgaABXWuSj0WtZ4Ev",
  "_version": 1,
  "_score": null,
  "_source": {
    "input": {
      "type": "log"
    },
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
          "subjectLogonId": "0x3e7",
          "subjectDomainName": "WORKGROUP",
          "targetLinkedLogonId": "0x4c9eb8",
          "impersonationLevel": "%%1833",
          "ipAddress": "::1",
          "authenticationPackageName": "Negotiate",
          "workstationName": "WINDOWS11",
          "targetLogonId": "0x4c9ee5",
          "logonProcessName": "CredPro",
          "logonGuid": "{00000000-0000-0000-0000-000000000000}",
          "targetUserName": "vboxuser",
          "keyLength": "0",
          "elevatedToken": "%%1843",
          "subjectUserSid": "S-1-5-18",
          "processId": "0xf8c",
          "processName": "C:\\\\Windows\\\\System32\\\\consent.exe",
          "ipPort": "0",
          "targetDomainName": "WINDOWS11",
          "targetUserSid": "S-1-5-21-4268055879-2565299617-812491912-1000",
          "virtualAccount": "%%1843",
          "logonType": "2",
          "subjectUserName": "WINDOWS11$"
        },
        "system": {
          "eventID": "4624",
          "keywords": "0x8020000000000000",
          "providerGuid": "{54849625-5478-4994-a5ba-3e3b0328c30d}",
          "level": "0",
          "channel": "Security",
          "opcode": "0",
          "message": "\"An account was successfully logged on.\r\n\r\nSubject:\r\n\tSecurity ID:\t\tS-1-5-18\r\n\tAccount Name:\t\tWINDOWS11$\r\n\tAccount Domain:\t\tWORKGROUP\r\n\tLogon ID:\t\t0x3E7\r\n\r\nLogon Information:\r\n\tLogon Type:\t\t2\r\n\tRestricted Admin Mode:\t-\r\n\tRemote Credential Guard:\t-\r\n\tVirtual Account:\t\tNo\r\n\tElevated Token:\t\tNo\r\n\r\nImpersonation Level:\t\tImpersonation\r\n\r\nNew Logon:\r\n\tSecurity ID:\t\tS-1-5-21-4268055879-2565299617-812491912-1000\r\n\tAccount Name:\t\tvboxuser\r\n\tAccount Domain:\t\tWINDOWS11\r\n\tLogon ID:\t\t0x4C9EE5\r\n\tLinked Logon ID:\t\t0x4C9EB8\r\n\tNetwork Account Name:\t-\r\n\tNetwork Account Domain:\t-\r\n\tLogon GUID:\t\t{00000000-0000-0000-0000-000000000000}\r\n\r\nProcess Information:\r\n\tProcess ID:\t\t0xf8c\r\n\tProcess Name:\t\tC:\\Windows\\System32\\consent.exe\r\n\r\nNetwork Information:\r\n\tWorkstation Name:\tWINDOWS11\r\n\tSource Network Address:\t::1\r\n\tSource Port:\t\t0\r\n\r\nDetailed Authentication Information:\r\n\tLogon Process:\t\tCredPro\r\n\tAuthentication Package:\tNegotiate\r\n\tTransited Services:\t-\r\n\tPackage Name (NTLM only):\t-\r\n\tKey Length:\t\t0\r\n\r\nThis event is generated when a logon session is created. It is generated on the computer that was accessed.\r\n\r\nThe subject fields indicate the account on the local system which requested the logon. This is most commonly a service such as the Server service, or a local process such as Winlogon.exe or Services.exe.\r\n\r\nThe logon type field indicates the kind of logon that occurred. The most common types are 2 (interactive) and 3 (network).\r\n\r\nThe New Logon fields indicate the account for whom the new logon was created, i.e. the account that was logged on.\r\n\r\nThe network fields indicate where a remote logon request originated. Workstation name is not always available and may be left blank in some cases.\r\n\r\nThe impersonation level field indicates the extent to which a process in the logon session can impersonate.\r\n\r\nThe authentication information fields provide detailed information about this specific logon request.\r\n\t- Logon GUID is a unique identifier that can be used to correlate this event with a KDC event.\r\n\t- Transited services indicate which intermediate services have participated in this logon request.\r\n\t- Package name indicates which sub-protocol was used among the NTLM protocols.\r\n\t- Key length indicates the length of the generated session key. This will be 0 if no session key was requested.\"",
          "version": "3",
          "systemTime": "2026-09-08T15:05:12.2213191Z",
          "eventRecordID": "27060",
          "threadID": "4672",
          "computer": "windows11",
          "task": "12544",
          "processID": "836",
          "severityValue": "AUDIT_SUCCESS",
          "providerName": "Microsoft-Windows-Security-Auditing"
        }
      }
    },
    "rule": {
      "mail": false,
      "level": 3,
      "pci_dss": [
        "10.2.5"
      ],
      "hipaa": [
        "164.312.b"
      ],
      "tsc": [
        "CC6.8",
        "CC7.2",
        "CC7.3"
      ],
      "description": "Windows Workstation Logon Success",
      "groups": [
        "windows",
        "windows_security",
        "authentication_success"
      ],
      "nist_800_53": [
        "AU.14",
        "AC.9"
      ],
      "gdpr": [
        "IV_32.2"
      ],
      "firedtimes": 4,
      "mitre": {
        "technique": [
          "Valid Accounts"
        ],
        "id": [
          "T1078"
        ],
        "tactic": [
          "Defense Evasion",
          "Persistence",
          "Privilege Escalation",
          "Initial Access"
        ]
      },
      "id": "60118",
      "gpg13": [
        "7.1",
        "7.2"
      ]
    },
    "location": "EventChannel",
    "decoder": {
      "name": "windows_eventchannel"
    },
    "id": "1788879914.199877",
    "timestamp": "2026-09-08T15:05:14.625+0000"
  },
  "fields": {
    "timestamp": [
      "2026-09-08T15:05:14.625Z"
    ]
  },
  "highlight": {
    "manager.name": [
      "@opensearch-dashboards-highlighted-field@wazuh-server@/opensearch-dashboards-highlighted-field@"
    ],
    "data.win.system.eventID": [
      "@opensearch-dashboards-highlighted-field@4624@/opensearch-dashboards-highlighted-field@"
    ]
  },
  "sort": [
    1788879914625
  ]
}