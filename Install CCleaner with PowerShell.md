# Install CCleaner with PowerShell

> Change the download location when a new version is released.
> https://www.piriform.com/ccleaner/download/standard

```
cd $env:userprofile\Downloads
$source = "http://download.piriform.com/ccsetup526.exe"
$destination = "$env:userprofile\Downloads\ccsetup526.exe"
Invoke-WebRequest $source -OutFile $destination
.\ccsetup.exe /S
Start-Sleep -s 15
exit
exit
```

## If you want you can also run a cleaning command:
> Auto Clean with CCleaner

```
cd $env:programfiles\CCleaner
.\CCleaner.exe /AUTO
Start-Sleep -s 15
exit
exit
```

# Run all commands:

```
cd $env:userprofile\Downloads
$source = "http://download.piriform.com/ccsetup526.exe"
$destination = "$env:userprofile\Downloads\ccsetup.exe"
Invoke-WebRequest $source -OutFile $destination
.\ccsetup.exe /S
Start-Sleep -s 15
cd $env:programfiles\CCleaner
.\CCleaner.exe /AUTO
Start-Sleep -s 15
exit
exit
```
