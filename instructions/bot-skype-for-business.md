
## Connecting Nowinfinity Assistant to your Skype for Business Online
<p align="center">
  <img align="bottom" alt="Nowinfinity Assistant" width="180" src="https://assistant.leo.nowinfinity.com.au/content/png_tr.png">
  <img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADAAAAAwCAYAAABXAvmHAAAAAXNSR0IArs4c6QAAAARnQU1BAACxjwv8YQUAAAAJcEhZcwAADsMAAA7DAcdvqGQAAAGNSURBVGhD7Zi/LgRRFIeHIBEaohOhRCREJEiUOoVqE1FpPIFICNH5U4kH0GrUOkqNxAMoSFApPQG+38SNs5PZanZm58j9kq/Yc3KT89vcnb13kkgkEmk33biNBziigjd28PvXFxxDV1xiCOAyxCx+ousQy+g+xBJmQzzj/wuxapxRwTCHobeigmEC7dqyPMQvbBnCNq5UMNxg6L2pYNhDu7Zqn7Afm4qeAkhtsaaCpwDvOIhJw7iogkH7PvTWVDBMol1blkeY/Q184BTWHg2pYePwVTONbocfx7zhFcoF5+h2eLGLbR1ej9J17Ek/lU8fKsQFFj64HWP4NnTRcMUJhuHlK7ohO7w8RRfkDa/t04W1Jw7fKfKGv8ZhHCrZ9EhsGEDbt+gRa3u9mOxjdvgq1Z3DojuJ7Vs20fbSI3720ly1hQPcm0InLBxAf9d6aWQb8hbPKnALLRto+xa9JbE93QpT8kJoa6WXZi/EEHWhVYgFdENeiAd0RTbEI7pjFHWkuMN5FSKRSCTyR5L8ADd4oN9HL2pnAAAAAElFTkSuQmCC">
  <img width="130" src="https://lh3.googleusercontent.com/5hqcg29p7TkwDWchqG41kMDgoa_IXSUgt9ilfft3ZF2scKW_9Jz5511HPAAqVbVKRQ=w180">
</p>
To add bot to Skype for Business, you must be the Tenant Administrator of a Skype for Business Online environment. Complete the following steps to add a bot:

- [Download and install the Skype for Business Online Connector module](http://go.microsoft.com/fwlink/?LinkId=294688)
- Open Windows PowerShell as Administrator and run the following:
```powershell
Import-PSSession (New-CsOnlineSession -Credential (Get-Credential))
```
- You will be prompted with windows PowerShell credential dialog box. Sign in using the tenant admin credentials.
- Run the following PowerShell command
```powershell
 New-CsOnlineApplicationEndpoint -ApplicationID 62516114-227c-436c-8e55-e7dcf50e7474 -Name "Rosie - Nowinfinity Assistant" -Uri sip:ni_assistant.bot@yourdomain.com
```
>This command registers an instance of our bot with a Skype for Business Online tenant. A Skype for Business Admin can replace the **_Uri_** parameter with a unique user account from their domain (eg. ni_assistant.bot@contoso.com)

_NOTE_: A newly registered bot can take up to 8 hours to be discoverable by all users in the Skype for Business tenant.
***
[//]: # (Resources: https://skypeappregistration.azurewebsites.net/bot/62516114-227c-436c-8e55-e7dcf50e7474 , https://msdn.microsoft.com/en-us/skype/Skype-For-Business-Bot-Framework/docs/overview)

