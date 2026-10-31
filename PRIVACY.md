# Hardware Pulse (Microsoft Store edition): Privacy Policy

[English](PRIVACY.md) · [简体中文](PRIVACY.zh-CN.md)

Last updated: 2026-10-31

Hardware Pulse reads hardware sensors on your PC and shows them locally. It has no account system, analytics, advertising or telemetry, and it does not upload sensor readings, hardware models, custom names, screenshots or usage history.

## Data processed on your PC

- **Sensor readings.** CPU, GPU, memory, storage, fan and network readings are read locally and kept in current snapshots under your user profile and, for Pro full sensors, under `%ProgramData%\HardwarePulseSensors`. Network readings use adapter byte counters only; packet contents are never inspected.
- **Screen sampling (optional).** Low Distraction and Local Contrast measure the brightness of the screen area behind the Desktop panel, in memory, to adjust text. Images are not saved or transmitted. While these features run, Windows excludes Pulse from screenshots; Screenshot mode lifts that for 15 seconds.
- **Settings and logs.** Settings, quota schedules and short diagnostic logs stay in `%LocalAppData%\HardwarePulse`. Diagnostic logs contain status categories and timings, never credentials or quota values.

## Network connections

- **AI Quota (opt-in per provider).** Codex and Claude read your existing local login and send its token only to their fixed quota endpoints at chatgpt.com or api.anthropic.com. Antigravity is read from its local language server over loopback. DeepSeek uses an API key you enter; it is encrypted with Windows DPAPI for your user and sent only to `https://api.deepseek.com/user/balance`. Each provider receives your IP address and User-Agent. Pulse performs no model calls, purchases or account changes.
- **PawnIO download (Pro, only when you press "Install PawnIO Driver").** The official installer is downloaded from github.com: first from its upstream release, then, if that fails, from the unmodified [mirror in this repository](https://github.com/medking82/hardware-pulse-legal/releases/tag/pawnio-2.2.0). GitHub receives your IP address and User-Agent. The file is run only after its SHA-256 matches the official file.
- **Microsoft Store.** The Pro license check and purchase use Microsoft Store services under Microsoft's privacy statement. Pulse receives only whether the Pro add-on is owned.

## System changes you start

- **Install PawnIO Driver** installs the PawnIO driver by namazso through Windows' administrator prompt.
- **Enable FPS** asks Windows to add your account to the built-in Performance Log Users group through the administrator prompt, so FPS can be read without running Pulse elevated. You can remove the account from that group in Computer Management at any time.

## Contact

Questions: https://github.com/medking82/hardware-pulse-legal/issues
