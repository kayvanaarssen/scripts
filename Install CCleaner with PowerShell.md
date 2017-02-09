# Install CCleaner with PowerShell

> Change the download location when a new version is released.
> https://www.piriform.com/ccleaner/download/standard

```
cd $env:userprofile\Downloads
$source = "http://download.piriform.com/ccsetup526.exe"
$destination = "$env:userprofile\Downloads\ccsetup526.exe"
Invoke-WebRequest $source -OutFile $destination
.\ccsetup526.exe /S
Start-Sleep -s 15
# Auto Clean with CCleaner
cd $env:programfiles\CCleaner
.\CCleaner.exe /AUTO
Start-Sleep -s 15
exit
```