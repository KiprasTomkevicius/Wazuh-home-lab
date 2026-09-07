{
  "_index": "wazuh-alerts-4.x-2026.09.07",
  "_id": "7-oHfaABPdJfxlT5Jw7Q",
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
          "subjectLogonId": "0x2a52b9",
          "clientProcessId": "9332",
          "subjectDomainName": "WINDOWS11",
          "auditPolicyChanges": "Success added",
          "subjectUserSid": "S-1-5-21-4268055879-2565299617-812491912-1001",
          "subcategoryId": "%%12800",
          "auditPolicyChangesId": "%%8449",
          "clientProcessStartKey": "2251799813686052",
          "category": "Object Access",
          "subcategory": "File System",
          "categoryId": "%%8274",
          "subjectUserName": "inside_account",
          "subcategoryGuid": "{0cce921d-69ae-11d9-bed3-505054503030}"
        },
        "system": {
          "eventID": "4719",
          "keywords": "0x8020000000000000",
          "providerGuid": "{54849625-5478-4994-a5ba-3e3b0328c30d}",
          "level": "0",
          "channel": "Security",
          "opcode": "0",
          "message": "\"System audit policy was changed.\r\n\r\nSubject:\r\n\tSecurity ID:\t\tS-1-5-21-4268055879-2565299617-812491912-1001\r\n\tAccount Name:\t\tinside_account\r\n\tAccount Domain:\t\tWINDOWS11\r\n\tLogon ID:\t\t0x2A52B9\r\n\r\nAudit Policy Change:\r\n\tCategory:\t\tObject Access\r\n\tSubcategory:\t\tFile System\r\n\tSubcategory GUID:\t{0cce921d-69ae-11d9-bed3-505054503030}\r\n\tChanges:\t\tSuccess Added\"",
          "version": "1",
          "systemTime": "2026-09-07T18:00:11.6544417Z",
          "eventRecordID": "26392",
          "threadID": "860",
          "computer": "windows11",
          "task": "13568",
          "processID": "824",
          "severityValue": "AUDIT_SUCCESS",
          "providerName": "Microsoft-Windows-Security-Auditing"
        }
      }
    },
    "rule": {
      "firedtimes": 1,
      "mail": false,
      "level": 8,
      "pci_dss": [
        "10.6.1"
      ],
      "hipaa": [
        "164.312.b"
      ],
      "tsc": [
        "CC7.2",
        "CC7.3"
      ],
      "description": "Windows Audit Policy changed",
      "groups": [
        "windows",
        "windows_security",
        "policy_changed"
      ],
      "id": "60112",
      "nist_800_53": [
        "AU.6"
      ],
      "gpg13": [
        "10.1"
      ],
      "gdpr": [
        "IV_35.7.d"
      ]
    },
    "location": "EventChannel",
    "decoder": {
      "name": "windows_eventchannel"
    },
    "id": "1788804013.139057",
    "timestamp": "2026-09-07T18:00:13.984+0000"
  },
  "fields": {
    "timestamp": [
      "2026-09-07T18:00:13.984Z"
    ]
  },
  "highlight": {
    "manager.name": [
      "@opensearch-dashboards-highlighted-field@wazuh-server@/opensearch-dashboards-highlighted-field@"
    ]
  },
  "sort": [
    1788804013984
  ]
}