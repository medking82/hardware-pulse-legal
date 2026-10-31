# Source Code

The Microsoft Store package of Hardware Pulse contains these open-source components. The exact upstream archives are attached to the [sources-0.6.76 release](https://github.com/medking82/hardware-pulse-legal/releases/tag/sources-0.6.76).

| Component | Version | License | Upstream source | Modified |
| --- | --- | --- | --- | --- |
| LibreHardwareMonitor | 0.9.6 | MPL-2.0 | https://github.com/LibreHardwareMonitor/LibreHardwareMonitor/tree/v0.9.6 | Yes, see below |
| BlackSharp.Core | 1.0.7 (commit c70b735c6cec123ee8a046ac4a0bc6c606f52cf0) | MPL-2.0 | https://github.com/Blacktempel/BlackSharp/tree/c70b735c6cec123ee8a046ac4a0bc6c606f52cf0 | Yes, see below |
| PresentMon console | 2.5.1 | MIT | https://github.com/GameTechDev/PresentMon/releases/tag/v2.5.1 | No |

## Local Modifications

Hardware Pulse changes two permission constants in the pinned upstream libraries so storage sensors open with minimum access, and replaces a direct AMD ADL PMLog pointer read with a guarded copy. These are read-only changes. They write no disk sectors, change no hardware settings and remove no sensors.

- [patches/STORAGE-ACCESS-PATCH.md](patches/STORAGE-ACCESS-PATCH.md): what changes and why
- [patches/StorageAccess.patch](patches/StorageAccess.patch) and [patches/AmdPmLog.patch](patches/AmdPmLog.patch): the source-level changes
- [patches/AmdPmLogMemory.cs.txt](patches/AmdPmLogMemory.cs.txt): the guarded PMLog read helper
- [patches/Patch-StorageAccess.ps1](patches/Patch-StorageAccess.ps1): the build step that applies the permission changes to the pinned binaries

## Not Included In The Package

**PawnIO 2.2.0** (GPL-2.0, by namazso) is not part of the Store package. On request, Hardware Pulse Pro downloads the official installer and runs it only if its SHA-256 is `1f519a22e47187f70a1379a48ca604981c4fcf694f4e65b734aaa74a9fba3032`.

- Upstream installer: https://github.com/namazso/PawnIO.Setup/releases/tag/2.2.0
- Upstream source: https://github.com/namazso/PawnIO/tree/2.2.0
- Mirror with the source archive: https://github.com/medking82/hardware-pulse-legal/releases/tag/pawnio-2.2.0
