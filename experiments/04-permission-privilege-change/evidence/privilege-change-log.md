{
  "_index": "wazuh-alerts-4.x-2026.09.05",
  "_id": "QKzocqABhEOiSSi7ey8R",
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
          "subjectLogonId": "0x44d59",
          "targetUserName": "Administrators",
          "memberSid": "S-1-5-21-4268055879-2565299617-812491912-1001",
          "subjectUserSid": "S-1-5-21-4268055879-2565299617-812491912-1000",
          "subjectDomainName": "WINDOWS11",
          "targetDomainName": "Builtin",
          "targetSid": "S-1-5-32-544",
          "subjectUserName": "vboxuser"
        },
        "system": {
          "eventID": "4732",
          "keywords": "0x8020000000000000",
          "providerGuid": "{54849625-5478-4994-a5ba-3e3b0328c30d}",
          "level": "0",
          "channel": "Security",
          "opcode": "0",
          "message": "\"A member was added to a security-enabled local group.\r\n\r\nSubject:\r\n\tSecurity ID:\t\tS-1-5-21-4268055879-2565299617-812491912-1000\r\n\tAccount Name:\t\tvboxuser\r\n\tAccount Domain:\t\tWINDOWS11\r\n\tLogon ID:\t\t0x44D59\r\n\r\nMember:\r\n\tSecurity ID:\t\tS-1-5-21-4268055879-2565299617-812491912-1001\r\n\tAccount Name:\t\t-\r\n\r\nGroup:\r\n\tSecurity ID:\t\tS-1-5-32-544\r\n\tGroup Name:\t\tAdministrators\r\n\tGroup Domain:\t\tBuiltin\r\n\r\nAdditional Information:\r\n\tPrivileges:\t\t-\"",
          "version": "0",
          "systemTime": "2026-09-05T18:50:28.9997689Z",
          "eventRecordID": "25682",
          "threadID": "880",
          "computer": "windows11",
          "task": "13826",
          "processID": "828",
          "severityValue": "AUDIT_SUCCESS",
          "providerName": "Microsoft-Windows-Security-Auditing"
        }
      }
    },
    "rule": {
      "mail": true,
      "level": 12,
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
      "description": "Administrators Group Changed",
      "groups": [
        "windows",
        "windows_security",
        "group_changed",
        "win_group_changed"
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
          "Domain Policy Modification"
        ],
        "id": [
          "T1484"
        ],
        "tactic": [
          "Defense Evasion",
          "Privilege Escalation"
        ]
      },
      "id": "60154",
      "gpg13": [
        "7.10"
      ]
    },
    "location": "EventChannel",
    "decoder": {
      "name": "windows_eventchannel"
    },
    "id": "1788634230.55198",
    "timestamp": "2026-09-05T18:50:30.874+0000"
  },
  "fields": {
    "timestamp": [
      "2026-09-05T18:50:30.874Z"
    ]
  },
  "highlight": {
    "manager.name": [
      "@opensearch-dashboards-highlighted-field@wazuh-server@/opensearch-dashboards-highlighted-field@"
    ],
    "data.win.eventdata.memberSid": [
      "@opensearch-dashboards-highlighted-field@S-1-5-21-4268055879-2565299617-812491912-1001@/opensearch-dashboards-highlighted-field@"
    ]
  },
  "sort": [
    1788634230874
  ]
}