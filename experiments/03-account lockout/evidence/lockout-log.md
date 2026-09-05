{
  "_index": "wazuh-alerts-4.x-2026.09.02",
  "_id": "DapHY6AB5d8D0BgzRJYz",
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
          "targetUserName": "inside_account",
          "subjectUserSid": "S-1-5-18",
          "subjectDomainName": "WORKGROUP",
          "targetDomainName": "WINDOWS11",
          "targetSid": "S-1-5-21-4268055879-2565299617-812491912-1001",
          "subjectUserName": "WINDOWS11$"
        },
        "system": {
          "eventID": "4740",
          "keywords": "0x8020000000000000",
          "providerGuid": "{54849625-5478-4994-a5ba-3e3b0328c30d}",
          "level": "0",
          "channel": "Security",
          "opcode": "0",
          "message": "\"A user account was locked out.\r\n\r\nSubject:\r\n\tSecurity ID:\t\tS-1-5-18\r\n\tAccount Name:\t\tWINDOWS11$\r\n\tAccount Domain:\t\tWORKGROUP\r\n\tLogon ID:\t\t0x3E7\r\n\r\nAccount That Was Locked Out:\r\n\tSecurity ID:\t\tS-1-5-21-4268055879-2565299617-812491912-1001\r\n\tAccount Name:\t\tinside_account\r\n\r\nAdditional Information:\r\n\tCaller Computer Name:\tWINDOWS11\"",
          "version": "0",
          "systemTime": "2026-09-02T18:00:04.1481868Z",
          "eventRecordID": "25255",
          "threadID": "8112",
          "computer": "windows11",
          "task": "13824",
          "processID": "848",
          "severityValue": "AUDIT_SUCCESS",
          "providerName": "Microsoft-Windows-Security-Auditing"
        }
      }
    },
    "rule": {
      "mail": false,
      "level": 9,
      "pci_dss": [
        "8.1.6",
        "11.4"
      ],
      "hipaa": [
        "164.312.a.1"
      ],
      "tsc": [
        "CC6.1",
        "CC6.8",
        "CC7.2",
        "CC7.3"
      ],
      "description": "User account locked out (multiple login errors)",
      "groups": [
        "windows",
        "windows_security",
        "authentication_failures"
      ],
      "nist_800_53": [
        "AC.7",
        "SI.4"
      ],
      "gdpr": [
        "IV_35.7.d"
      ],
      "firedtimes": 1,
      "mitre": {
        "technique": [
          "Brute Force",
          "Account Access Removal"
        ],
        "id": [
          "T1110",
          "T1531"
        ],
        "tactic": [
          "Credential Access",
          "Impact"
        ]
      },
      "id": "60115",
      "gpg13": [
        "7.5"
      ]
    },
    "location": "EventChannel",
    "decoder": {
      "name": "windows_eventchannel"
    },
    "id": "1788372005.356785",
    "timestamp": "2026-09-02T18:00:05.988+0000"
  },
  "fields": {
    "timestamp": [
      "2026-09-02T18:00:05.988Z"
    ]
  },
  "highlight": {
    "rule.mitre.technique": [
      "@opensearch-dashboards-highlighted-field@Brute Force@/opensearch-dashboards-highlighted-field@"
    ],
    "manager.name": [
      "@opensearch-dashboards-highlighted-field@wazuh-server@/opensearch-dashboards-highlighted-field@"
    ],
    "agent.name": [
      "@opensearch-dashboards-highlighted-field@SOC-Windows11@/opensearch-dashboards-highlighted-field@"
    ]
  },
  "sort": [
    1788372005988
  ]
}