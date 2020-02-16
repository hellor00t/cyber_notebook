# Splunk Cheatsheets

Setup

* Add sysmon macro
`index=<index> sourcetype="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" `

## General

* List Indices

`| eventcount summarize=false index=* index=_* | dedup index | fields index`

* Identify index sourcetypes
`| metadata type=sourcetypes index=<index name>`

## Windows

* List of interesting processes from sysmon

``sysmon` Image=*\\powershell.exe OR Image=*\\msbuild.exe OR Image=*\\psexec.exe OR Image=*\\at.exe OR Image=*\\schtasks.exe OR Image=*\\net.exe OR Image=*\\vssadmin.exe OR Image=*\\utilman.exe OR Image=*\\wmic.exe OR Image=*\\mshta.exe OR Image=*\\wscript.exe OR Image=*\\cscript.exe OR Image=*\\cmd.exe OR Image=*\\whoami.exe OR Image=*\\mmc.exe OR Image=*\\systeminfo.exe OR Image=*\\csvde.exe OR Image=*\\certutil.exe | stats values(CommandLine) by Image`

### Sysmon

* Count Sysmon EventIDs and Descriptions

``sysmon` | stats count by EventID, EventDescription`

## Linux

## Network