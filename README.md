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

## Setting up Remote access for Teams Rooms Console

## Relevanted links
* [MTR devices](https://www.microsoft.com/en-us/microsoft-365/microsoft-teams/across-devices/devices) 
* [MTR release notes](https://docs.microsoft.com/en-us/microsoftteams/rooms/rooms-release-note) 
* [MTR maintenance and operations](https://docs.microsoft.com/en-us/microsoftteams/rooms/rooms-operations#RemotePS) 
* [MTR XML config file](https://docs.microsoft.com/en-us/MicrosoftTeams/rooms/xml-config-file) 
