
## Connecting your bot to Skype for Business Online
<p align="center">
  <img align="bottom" alt="Nowinfinity Assistant" width="300" src="https://assistant.leo.nowinfinity.com.au/content/png_tr.png">
</p>
To add your bot to Skype for Business, you must be the Tenant Administrator of a Skype for Business Online environment. Complete the following steps to add a bot:

1. [Download and install the Skype for Business Online Connector module](Download%20and%20install%20the%20Skype%20for%20Business%20Online%20Connector%20module)
2. Open Windows PowerShell as Administrator and run the following:
```ps
Import-PSSession (New-CsOnlineSession -Credential (Get-Credential))
```
3. You will be prompted with windows PowerShell credential dialog box. Sign in using the tenant admin credentials.
4. Run the following PowerShell cmdlet
```ps
 New-CsOnlineApplicationEndpoint -ApplicationID 62516114-227c-436c-8e55-e7dcf50e7474 -Name "Rosie - Nowinfinity Assistant" -Uri sip:<ni.assistant.bot@yourdomain.com>
```
>This command registers an instance of your bot with a Skype for Business Online tenant. A Skype for Business Admin can replace the **_Name_** parameter with their desired bot display name and replace the **_Uri_** parameter with a unique user account from their domain (eg. mybot@contoso.com)

NOTE: A newly registered bot can take up to 8 hours to be discoverable by all users in the Skype for Business tenant. More details on using PowerShell to manage bots and apps for Skype for Business can be found [here](https://msdn.microsoft.com/en-us/skype/trusted-application-api/docs/trustedapplicationendpoint)
***
