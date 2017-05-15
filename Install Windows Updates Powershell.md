PowerShell for Windows updates? Why would you want to do this other than the fact that it’s a cool thing to do? Well it’s fairly easy to do and can be easilly automated.

Firstly you will need version 5 of PowerShell which is apart of Windows 10. Since version 5 you can now download and install modules online from the PowerShell Gallery.

First thing you need to do is confirm the version of PowerShell you have:

`$PSVersionTable.PSVersion`

If version 5 or above, confirm you are running PowerShell as administrator and continue with:

```powershell
Install-Module PSWindowsUpdate
Get-Command –module PSWindowsUpdate
```

Then you will need to register to use the Microsoft Update Service not just the default Windows Update Service.

`Add-WUServiceManager -ServiceID 7971f918-a847-4430-9279-4a52d1efe18d`

Then run:

`Get-WUInstall –MicrosoftUpdate –AcceptAll –AutoReboot`

More info here: https://www.petri.com/manage-windows-updates-with-powershell-module
