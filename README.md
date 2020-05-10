# Microsoft Teams Rooms (MTR)
Configurations and hints


## Creating and preparing room account
It has to be configured, otherwise MTR will show the Organizer as Subject
```
Set-CalendarProcessing -Identity "Conf" -DeleteSubject $False -AddOrganizerToSubject $False
```
It has to be configured, otherwise MTR will not accept external meeting invitations
```
Set-CalendarProcessing -Identity "Conf" -ProcessExternalMeetingMessages $true
```


## Setting up the Teams Rooms Console

## Updating Teams Rooms Console

### With Microsoft Store
Search for Microsoft Store in your Windows 10 enviroment and then the dots icon (...) and click on Downloads. 
There you should find the app Skype Rooms Systems which is actually Teams Rooms Console.

### Manually with PS
At first you need the [Skype Room System Deployment Kit](https://go.microsoft.com/fwlink/?linkid=851168). 
After the download the location for the files is `C:\Program Files (x86)\Skype Room System Deployment Kit`
You can find the reference document [here](https://docs.microsoft.com/en-us/microsoftteams/rooms/rooms-operations#to-update-using-powershell).
I prefere to do this locally directly on the MTR client, so copy the content e.g. in `C:\Temp` and execute:
```
Add-AppxPackage -ForceApplicationShutdown -Path 'C:\Skype Room System Deployment Kit\Temp\$oem$\$1\Rigel\x64\Ship\AppPackages\*\*.appx' -DependencyPath (Get-ChildItem 'C:\Temp\Skype Room System Deployment Kit\$oem$\$1\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx' | Foreach-Object {$_.FullName})
```
After execute, you won"t see any messages, so just restart the hardware and check the App version in MTR.

## Setting up Remote access for Teams Rooms Console


## Additional setting
It is possible to create a easier experience for [booking rooms in Outlook](https://techcommunity.microsoft.com/t5/exchange-team-blog/easier-room-booking-in-outlook-on-the-web/ba-p/743349).
```
Set-Place -Identity "Conf-Room" -AudioDeviceName $null -City "Melbourne" -CountryOrRegion "Australia" -DisplayDeviceName "HP Elite Slice G2" -FloorLabel "Second Level" -GeoCoordinates "-37.8456457; 144.9777676" -IsWheelChairAccessible $true -PostalCode "VIC 3004" -State "Victoria" -Street "XXX St Kilda Rd" -VideoDeviceName $null
```
Also you can add this room to a distributiongroup only for rooms, which will detect as catagory in Outlook
```
Add-DistributionGroupMember -Identity “Rooms In Melbourne“ -Member conf-room@xxx.com
```



## Relevanted links
* [MTR devices](https://www.microsoft.com/en-us/microsoft-365/microsoft-teams/across-devices/devices) 
* [MTR release notes](https://docs.microsoft.com/en-us/microsoftteams/rooms/rooms-release-note) 
* [MTR maintenance and operations](https://docs.microsoft.com/en-us/microsoftteams/rooms/rooms-operations#RemotePS) 
* [MTR XML config file](https://docs.microsoft.com/en-us/MicrosoftTeams/rooms/xml-config-file) 
