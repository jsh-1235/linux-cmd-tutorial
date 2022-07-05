# login

- quser

- gpedit.msc (Local Group Editor)
  - Computer Configuration -> Windows Settings -> Security Settings -> Local Policy -> Audit Policy -> Audit login events
  - Audit these attempts : Success, Failure

- eventvwr.msc (Event Viewer)
  - Windows Logs -> Security
  - Windows Logs -> System
    - Filter -> Event Source -> [Winlogon]
    - Event ID : 7001
