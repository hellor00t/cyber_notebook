# Splunk Cheatsheets

Setup

* Add sysmon macro

  `index=<index> sourcetype="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational"`

## General

* List Indices

`| eventcount summarize=false index=* index=_* | dedup index | fields index`

* Identify index sourcetypes

  `| metadata type=sourcetypes index=<index name>`

## Windows

* List of interesting processes from sysmon

```sysmon`` Image=_\powershell.exe OR Image=_\msbuild.exe OR Image=_\psexec.exe OR Image=_\at.exe OR Image=_\schtasks.exe OR Image=_\net.exe OR Image=_\vssadmin.exe OR Image=_\utilman.exe OR Image=_\wmic.exe OR Image=_\mshta.exe OR Image=_\wscript.exe OR Image=_\cscript.exe OR Image=_\cmd.exe OR Image=_\whoami.exe OR Image=_\mmc.exe OR Image=_\systeminfo.exe OR Image=_\csvde.exe OR Image=_\certutil.exe \| stats values\(CommandLine\) by Image\`

### Sysmon

* Count Sysmon EventIDs and Descriptions

```sysmon`` \| stats count by EventID, EventDescription\`

## Linux

## Network

