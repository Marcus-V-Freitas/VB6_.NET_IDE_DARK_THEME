# VB6 / .NET IDE Dark Theme

> 🇧🇷 [Leia em Português](README.pt-br.md)

[![License](https://img.shields.io/badge/license-MIT-blue)](LICENSE)
![Platform](https://img.shields.io/badge/platform-Windows-blue)
![Target](https://img.shields.io/badge/IDE-VB6%20%7C%20.NET%20Classic-blue)

A dark color theme for the Visual Basic 6 and classic .NET IDEs, applied via a patched
`VBA6.DLL` and a registry import. No third-party tools required.

## Motivation

The VB6 and classic .NET IDEs (VB.NET, C# in the legacy IDE) ship with a fixed white
background editor that cannot be changed through the IDE options alone. The only way to get
a proper dark theme is to patch `VBA6.DLL` to unlock custom color support and then import
the color palette via the Windows Registry.

This repository packages the patched DLL, the registry file and the color configuration so
the entire setup takes less than five minutes.

## Repository Contents

| File | Description |
|---|---|
| `VBA6.DLL` | Patched DLL with custom color support enabled |
| `Run.reg` | Windows Registry file with the dark color palette |
| `Tema Dark.ini` | Raw color palette definition (RGBA values) |
| `Backup/VBA6.DLL` | Original unmodified DLL for rollback |

## Installation

> **Prerequisites:** Visual Basic 6 or the classic .NET IDE installed on Windows.

1. Close the IDE completely before starting.

2. Back up your current `VBA6.DLL` (already included in `Backup/` as reference):
```
C:\Windows\System32\VBA6.DLL
```

3. Copy the patched `VBA6.DLL` from this repository to the same path:
```
copy VBA6.DLL C:\Windows\System32\VBA6.DLL
```
> You may need to take ownership of the file or run the command as Administrator.

4. Double-click `Run.reg` and confirm the registry import when prompted.

5. Open the IDE. The editor will now use the dark color scheme.

## Color Palette

The theme is applied with the following colors, defined in `Tema Dark.ini` and `Run.reg`:

| Role | Color |
|---|---|
| Background | `#1E1E1E` (dark gray) |
| Foreground / Normal text | `#D4D4D4` (light gray) |
| Keywords | `#569CD6` (blue) |
| Comments | `#608B4E` (green) |
| Strings | `#D69D85` (peach) |
| Errors | `#FF0000` (red) |
| Selection | `#264F78` (dark blue) |
| Font | Consolas 10pt |

## Rollback

To revert to the original IDE appearance:

1. Copy `Backup/VBA6.DLL` back to `C:\Windows\System32\VBA6.DLL`.
2. Open the IDE Options and reset the editor colors manually, or re-import the original
   registry keys.

## License

[MIT](LICENSE)
