# Plugins

## Archon

[`install.ps1`](install.ps1) is the Windows PowerShell installer for the
[Archon](https://github.com/coleam00/Archon) CLI (vendored from `Archon-dev.zip`
in this repo). It downloads the latest `archon` release binary from GitHub,
verifies its checksum, and adds it to your user `PATH`.

```powershell
irm https://archon.diy/install.ps1 | iex
```
