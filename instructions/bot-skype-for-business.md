
## Connecting Nowinfinity Assistant to your Skype for Business Online
<p align="center">
  <img align="middle" alt="Nowinfinity Assistant" width="180" src="https://assistant.leo.nowinfinity.com.au/content/png_tr.png">
</p>
To add bot to Skype for Business, you must be the Tenant Administrator of a Skype for Business Online environment. Complete the following steps to add a bot:

* [Download and install the Skype for Business Online Connector module](http://go.microsoft.com/fwlink/?LinkId=294688)
* Open Windows PowerShell as Administrator and run the following: ``Import-PSSession (New-CsOnlineSession -Credential (Get-Credential))``
* You will be prompted with windows PowerShell credential dialog box. Sign in using the tenant admin credentials.
* Run the following PowerShell command: ``New-CsOnlineApplicationEndpoint -ApplicationID 62516114-227c-436c-8e55-e7dcf50e7474 -Name "Rosie - Nowinfinity Assistant" -Uri sip:ni_assistant.bot@yourdomain.com``
>This command registers an instance of our bot with a Skype for Business Online tenant. A Skype for Business Admin can replace the **_Uri_** parameter with a unique user account from their domain (eg. ni_assistant.bot@contoso.com)

_NOTE_: A newly registered bot can take up to 8 hours to be discoverable by all users in the Skype for Business tenant.
***
[//]: # (Resources: https://skypeappregistration.azurewebsites.net/bot/62516114-227c-436c-8e55-e7dcf50e7474 , https://msdn.microsoft.com/en-us/skype/Skype-For-Business-Bot-Framework/docs/overview)

