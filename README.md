# LUX - Notice Creator

LUX - Notice Creator is a Windows add-in for Microsoft Excel and Word. It turns selected household rows in a relocation schedule into editable Word notices, one file per unit, from each project's Word templates.

This repository publishes the installer. Each release contains three files:

| File | Purpose |
|---|---|
| `LUX-Notice-Creator-Setup.exe` | Installs, updates, or repairs the add-in for the current Windows user |
| `LUX-Notice-Creator-Release.json` | Version, size, SHA-256 checksum, and download address read by the add-in's update check |
| `LUX-Notice-Creator-Setup.sha256.txt` | SHA-256 checksum of the installer |

## Install

1. Download `LUX-Notice-Creator-Setup.exe` from the [latest release](https://github.com/CrystalCanvas/LUX-Notice-Creator/releases/latest).
2. Close Excel and Word.
3. Run the file and click **Install**. Setup installs for the current Windows user and does not ask for administrator rights.

The installer is not code-signed yet, so Windows SmartScreen can show "Windows protected your PC". Choose **More info**, then **Run anyway**.

Requirements: Windows 10 or 11, desktop Excel and Word 2016 or newer, and .NET Framework 4.8.

## Updates

Version 0.2.34 and later update themselves. About once a day the add-in checks this repository for a newer release. It downloads the installer, confirms that its size, SHA-256 checksum, and version match the release information, and installs it after Excel and Word are closed. Templates, generated notices, and settings stay on the computer, and setup keeps the previous version so it can be restored.

Copies older than 0.2.34 need the new installer run by hand once.

## Check a download

In PowerShell:

```powershell
Get-FileHash .\LUX-Notice-Creator-Setup.exe -Algorithm SHA256
```

The result must match `LUX-Notice-Creator-Setup.sha256.txt` from the same release.
