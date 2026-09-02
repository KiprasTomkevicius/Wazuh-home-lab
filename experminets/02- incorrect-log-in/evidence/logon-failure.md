{
  _index wazuh-alerts-4.x-2026.09.02,
  _id 0HQxYqABkhzGTtGXMT1K,
  _version 1,
  _score null,
  _source {
    input {
      type log
    },
    agent {
      ip 192.168.56.108,
      name SOC-Windows11,
      id 001
    },
    manager {
      name wazuh-server
    },
    data {
      win {
        eventdata {
          subjectLogonId 0x3e7,
          subjectDomainName WORKGROUP,
          ipAddress 127.0.0.1,
          authenticationPackageName Negotiate,
          workstationName WINDOWS11,
          subStatus 0xc000006a,
          logonProcessName User32,
          targetUserName inside_account,
          keyLength 0,
          subjectUserSid S-1-5-18,
          processId 0x65c,
          processName CWindowsSystem32svchost.exe,
          ipPort 0,
          failureReason %%2313,
          targetDomainName WINDOWS11,
          targetUserSid S-1-0-0,
          logonType 2,
          subjectUserName WINDOWS11$,
          status 0xc000006d
        },
        system {
          eventID 4625,
          keywords 0x8010000000000000,
          providerGuid {54849625-5478-4994-a5ba-3e3b0328c30d},
          level 0,
          channel Security,
          opcode 0,
          message An account failed to log on.rnrnSubjectrntSecurity IDttS-1-5-18rntAccount NamettWINDOWS11$rntAccount DomainttWORKGROUPrntLogon IDtt0x3E7rnrnLogon Typettt2rnrnAccount For Which Logon FailedrntSecurity IDttS-1-0-0rntAccount Namettinside_accountrntAccount DomainttWINDOWS11rnrnFailure InformationrntFailure ReasonttUnknown user name or bad password.rntStatusttt0xC000006DrntSub Statustt0xC000006ArnrnProcess InformationrntCaller Process IDt0x65crntCaller Process NametCWindowsSystem32svchost.exernrnNetwork InformationrntWorkstation NametWINDOWS11rntSource Network Addresst127.0.0.1rntSource Porttt0rnrnDetailed Authentication InformationrntLogon ProcessttUser32 rntAuthentication PackagetNegotiaterntTransited Servicest-rntPackage Name (NTLM only)t-rntKey Lengthtt0rnrnThis event is generated when a logon request fails. It is generated on the computer where access was attempted.rnrnThe Subject fields indicate the account on the local system which requested the logon. This is most commonly a service such as the Server service, or a local process such as Winlogon.exe or Services.exe.rnrnThe Logon Type field indicates the kind of logon that was requested. The most common types are 2 (interactive) and 3 (network).rnrnThe Process Information fields indicate which account and process on the system requested the logon.rnrnThe Network Information fields indicate where a remote logon request originated. Workstation name is not always available and may be left blank in some cases.rnrnThe authentication information fields provide detailed information about this specific logon request.rnt- Transited services indicate which intermediate services have participated in this logon request.rnt- Package name indicates which sub-protocol was used among the NTLM protocols.rnt- Key length indicates the length of the generated session key. This will be 0 if no session key was requested.,
          version 0,
          systemTime 2026-09-02T125619.3397645Z,
          eventRecordID 24918,
          threadID 9920,
          computer windows11,
          task 12544,
          processID 832,
          severityValue AUDIT_FAILURE,
          providerName Microsoft-Windows-Security-Auditing
        }
      }
    },
    rule {
      mail false,
      level 5,
      pci_dss [
        10.2.4,
        10.2.5
      ],
      hipaa [
        164.312.b
      ],
      tsc [
        CC6.1,
        CC6.8,
        CC7.2,
        CC7.3
      ],
      description Logon Failure - Unknown user or bad password,
      groups [
        windows,
        windows_security,
        authentication_failed
      ],
      nist_800_53 [
        AU.14,
        AC.7
      ],
      gdpr [
        IV_35.7.d,
        IV_32.2
      ],
      firedtimes 6,
      mitre {
        technique [
          Account Access Removal
        ],
        id [
          T1531
        ],
        tactic [
          Impact
        ]
      },
      id 60122,
      gpg13 [
        7.1
      ]
    },
    location EventChannel,
    decoder {
      name windows_eventchannel
    },
    id 1788353782.129921,
    timestamp 2026-09-02T125622.252+0000
  },
  fields {
    timestamp [
      2026-09-02T125622.252Z
    ]
  },
  highlight {
    data.win.eventdata.logonType [
      @opensearch-dashboards-highlighted-field@2@opensearch-dashboards-highlighted-field@
    ],
    manager.name [
      @opensearch-dashboards-highlighted-field@wazuh-server@opensearch-dashboards-highlighted-field@
    ]
  },
  sort [
    1788353782252
  ]
}