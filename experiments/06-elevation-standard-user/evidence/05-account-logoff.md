{
  "_index": "wazuh-alerts-4.x-2026.09.08",
  "_id": "Qe2NgaABXWuSj0WtZ4Ev",
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
          "targetLogonId": "0x4c9ee5",
          "targetUserName": "vboxuser",
          "targetDomainName": "WINDOWS11",
          "targetUserSid": "S-1-5-21-4268055879-2565299617-812491912-1000",
          "logonType": "2"
        },
        "system": {
          "eventID": "4634",
          "keywords": "0x8020000000000000",
          "providerGuid": "{54849625-5478-4994-a5ba-3e3b0328c30d}",
          "level": "0",
          "channel": "Security",
          "opcode": "0",
          "message": "\"An account was logged off.\r\n\r\nSubject:\r\n\tSecurity ID:\t\tS-1-5-21-4268055879-2565299617-812491912-1000\r\n\tAccount Name:\t\tvboxuser\r\n\tAccount Domain:\t\tWINDOWS11\r\n\tLogon ID:\t\t0x4C9EE5\r\n\r\nLogon Type:\t\t\t2\r\n\r\nThis event is generated when a logon session is destroyed. It may be positively correlated with a logon event using the Logon ID value. Logon IDs are only unique between reboots on the same computer.\"",
          "version": "0",
          "systemTime": "2026-09-08T15:05:12.2215963Z",
          "eventRecordID": "27062",
          "threadID": "1812",
          "computer": "windows11",
          "task": "12545",
          "processID": "836",
          "severityValue": "AUDIT_SUCCESS",
          "providerName": "Microsoft-Windows-Security-Auditing"
        }
      }
    },
    "rule": {
      "firedtimes": 2,
      "mail": false,
      "level": 3,
      "description": "Non service account logged off.",
      "groups": [
        "windows",
        " WEF"
      ],
      "id": "67023"
    },
    "location": "EventChannel",
    "decoder": {
      "name": "windows_eventchannel"
    },
    "id": "1788879914.210600",
    "timestamp": "2026-09-08T15:05:14.674+0000"
  },
  "fields": {
    "timestamp": [
      "2026-09-08T15:05:14.674Z"
    ]
  },
  "highlight": {
    "manager.name": [
      "@opensearch-dashboards-highlighted-field@wazuh-server@/opensearch-dashboards-highlighted-field@"
    ],
    "data.win.system.eventID": [
      "@opensearch-dashboards-highlighted-field@4634@/opensearch-dashboards-highlighted-field@"
    ]
  },
  "sort": [
    1788879914674
  ]
}