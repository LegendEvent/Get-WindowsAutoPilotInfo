# Enhanced Get-WindowsAutoPilotInfo Script

## Overview

This repository contains an enhanced version of the `Get-WindowsAutoPilotInfo` script, originally from the [PowerShell Gallery](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo/3.9). The main enhancement is the addition of a backslash escape feature for GroupTags, allowing the use of GroupTags like "DEU\HB1" without issues.

## Key Features

- All original functionality of the Get-WindowsAutoPilotInfo script
- Improved handling of GroupTags containing backslashes

## Usage

To use this enhanced version:

1. Download the `Get-WindowsAutoPilotInfo.ps1` file from this repository.
2. Replace the original script file located at `C:\Program Files\WindowsPowerShell\Scripts\Get-WindowsAutoPilotInfo.ps1` with the downloaded file.

## Important Note

This script is intended to replace the original script in your system. Make sure to backup the original script before replacing it.

## Changes from Original

The main change is in the handling of the GroupTag parameter. The relevant code snippet now looks like this:

```powershell
$imported += Add-AutopilotImportedDevice -serialNumber $_.'Device Serial Number' -hardwareIdentifier $_.'Hardware Hash' -groupTag ($_.'Group Tag' -replace '\\', '\\') -assignedUser $_.'Assigned User'
```
This modification allows for the correct handling of GroupTags containing backslashes.

## Credits

All credits for the original script go to the authors at the PowerShell Gallery. This repository only adds the escape feature for improved GroupTag handling.

## License
This project is licensed under the MIT License. See the LICENSE file for details.

## Disclaimer

This is an unofficial enhancement. Always ensure you're using scripts from trusted sources and test thoroughly in a non-production environment before deploying to production systems.
