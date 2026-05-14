# OBS Studio - Complete Beginner's Guide

> *For new streamers and video creators | OBS Studio (free & open source)*

**OBS Studio** (Open Broadcaster Software) is a free, open-source program for recording and live streaming. It works on Windows, Mac, and Linux and is used by millions of creators on Twitch, YouTube, Kick, and more.

### Download & Install

1. Go to https://obsproject.com
2. Click your operating system (Windows / Mac / Linux)
3. Run the installer and follow the prompts
4. Launch OBS Studio when done

## Understanding the OBS Interface

When you open OBS for the first time, you'll see several key panels:

```
┌─────────────────────────────────────┐
│           Preview Window            │  ← stream/recording view
├──────────────┬──────────────────────┤
│    Scenes    │      Sources         │  ← What's on screen
├──────────────┴──────────────────────┤
│  Audio Mixer │  Scene Transitions   │  ← Sound controls
├─────────────────────────────────────┤
│         Controls (bottom right)     │  ← Start/Stop buttons
└─────────────────────────────────────┘
```

- **Scenes** — Different "layouts" you can switch between (e.g., gameplay, webcam, BRB screen)
- **Sources** — Everything visible in a scene (game capture, webcam, images, text)
- **Audio Mixer** — Controls microphone and desktop audio levels
- **Controls** — Start/stop streaming or recording

## Auto-Configuration Wizard

When you first open OBS, it will offer to run the Auto-Configuration Wizard.

Run it. Here's what it does:

- Tests your PC's performance
- Recommends the best settings for your internet speed
- Sets up your output resolution and bitrate automatically

To run it manually later: `Tools` → `Auto-Configuration Wizard`

## Scenes & Sources Explained

Think of Scenes as TV "sets." You can have multiple scenes and switch between them live.

**Common scenes to create:**

- `Gameplay` - your game + mic + optional webcam
- `Just Chatting` - webcam fullscreen
- `BRB` - a holding screen for breaks
- `Starting Soon` - countdown or waiting screen
- `Stream Ending` - outro screen

**To add a scene:**

> Click the **+** button at the bottom of the Scenes panel → name it → hit OK

### Sources

**Sources** are the building blocks inside each scene.

**Most common source types:**

| Source Type | Use |
|---|---|
| `Game Capture` | Captures a specific game (best for gaming) |
| `Display Capture` | Captures your entire monitor |
| `Window Capture` | Captures a specific app window |
| `Video Capture Device` | Your webcam |
| `Audio Input Capture` | Your microphone |
| `Image` | Logos, overlays, borders |
| `Text (GDI+)` | On-screen text labels |
| `Browser` | Alerts, chat widgets, Streamlabs/StreamElements overlays |
| `Media Source` | Video files, looping animations |

**To add a source:**

> Click **+** in the Sources panel → choose type → name it → configure it
>
> Sources are layered. Drag them up/down in the list to control what appears on top.

## Setting Up Your Audio

Good audio is more important than video quality. Viewers will tolerate bad video, they won't tolerate bad audio.

### Microphone Setup

1. In the Audio Mixer, find your mic (usually labeled `Mic/Aux`)
2. Speak normally - your levels should sit in the yellow zone (-20 to -6 dB)
3. Avoid hitting the red zone (that's clipping/distortion)

### Desktop Audio

- `Desktop Audio` captures all sounds from your PC (game audio, music, etc.)
- Keep this at a lower volume than your mic so your voice is always clear

### Noise Suppression (Highly Recommended)

> Right-click your mic in the Audio Mixer → `Filters` → click `+` → add Noise Suppression

This removes background hum, fan noise, keyboard clicks, etc.

**Other useful audio filters:**

- **Gain** - boosts a quiet mic
- **Compressor** - evens out loud/quiet differences in your voice
- **Limiter** - prevents audio from ever peaking into the red

## Adding Your Webcam

1. In your scene, click + in Sources
2. Choose Video Capture Device
3. Name it (e.g., `Webcam`) → OK
4. Select your webcam from the Device dropdown
5. Click OK - your webcam will appear in the preview
6. Resize and reposition it by dragging the red handles

> Tip: Hold `Shift` while dragging a corner handle to crop your webcam view.

## Output Settings (Recording & Streaming)

Go to `File` → `Settings` → `Output`

### For Streaming

| Setting | Value |
|---|---|
| Encoder | `x264` (CPU) or `NVENC` (NVIDIA GPU) |
| Bitrate | 4500–6000 Kbps (Twitch) / 6000–8000 Kbps (YouTube) |
| Keyframe Interval | `2` seconds |
| Preset | `veryfast` or `faster` (for x264) |

### For Recording

| Setting | Value |
|---|---|
| Recording Format | `MKV` (safest) or `MP4` |
| Encoder | NVENC or x264 |
| Quality | `High Quality, Medium File Size` (CRF mode) |

> MKV vs MP4: Record in MKV first. If OBS crashes, MKV files are recoverable. MP4 files are not. You can remux MKV → MP4 in OBS after recording: `File` → `Remux Recordings`

## Video Settings

Go to `File` → `Settings` → `Video`

| Setting | Value |
|---|---|
| Base (Canvas) Resolution | Match your monitor (e.g., `1920x1080`) |
| Output (Scaled) Resolution | `1920x1080` or `1280x720` |
| Downscale Filter | `Lanczos` (best quality) |
| FPS | `60` for gaming, `30` for casual/chatting |

> If your PC struggles, lower the Output Resolution to `1280x720` before lowering FPS.

## Connecting to Twitch / YouTube

### Twitch

1. Go to `File` → `Settings` → `Stream`
2. Set Service to `Twitch`
3. Click Connect Account and log in
   - Or paste your Stream Key from Twitch Dashboard manually

### YouTube

1. Set Service to `YouTube - RTMPS`
2. Click Get Stream Key - it opens YouTube Studio
3. Copy your stream key and paste it back in OBS

> Never share your stream key. Anyone with it can stream to your channel.

## Overlays & Alerts

Overlays add graphics to your stream (borders, alerts, animated elements).

### Free overlay tools:

- Streamlabs - streamlabs.com (free alerts, overlays)
- StreamElements - streamelements.com (free, browser-source based)
- Nerd or Die / OWN3D - premade overlay packs

### Adding alerts (e.g., follower/sub alerts) in OBS:

1. Set up alerts in Streamlabs or StreamElements
2. Copy the Widget URL they give you
3. In OBS: add a Browser source → paste the URL
4. Set width/height to `1920x1080`

## Hotkeys (Game Changers)

Set up hotkeys so you don't need to click OBS while live.

Go to `File` → `Settings` → `Hotkeys`

Recommended hotkeys to set:

| Action | Hotkey |
|---|---|
| Start/Stop Streaming | `F9` |
| Start/Stop Recording | `F8` |
| Mute Mic | `F1` or `Ctrl+M` |
| Switch to Scene 1 | `Numpad 1` |
| Switch to Scene 2 | `Numpad 2` |

## Pre-Stream Checklist

Use this before going live every time:

```
[ ] OBS is showing the correct scene
[ ] Game/application is captured and visible in preview
[ ] Webcam is on and positioned correctly
[ ] Mic levels are in the yellow (not red)
[ ] Desktop audio is audible but not too loud
[ ] Stream title and category are updated on your platform
[ ] Alerts/overlays are loaded (test them!)
[ ] Hotkeys are working
[ ] Run a 30-second test recording to check audio + video sync
```

## Common Problems & Fixes

### ✗ Game not showing up in Game Capture

- Try switching to Display Capture temporarily
- Make sure OBS is running as Administrator
- Some games (anti-cheat protected) need Display Capture instead

### ✗ Stream is laggy / dropping frames

- Lower your bitrate in Output settings
- Switch encoder from `x264` to `NVENC` (if you have an NVIDIA GPU)
- Close background apps (Discord video, Chrome with many tabs, etc.)
- Check your internet upload speed — you need at least 2x your bitrate

### ✗ Audio out of sync

- Go to `File` → `Settings` → `Advanced` → set Audio Monitoring correctly
- Add a Sync Offset to your video source (right-click source → Properties)
- As a quick fix: record a short clip, measure the offset, apply it

### ✗ Black screen on Game/Display Capture

- Right-click OBS in taskbar → run with high-performance GPU
- On laptops: go to Windows GPU settings → set OBS to use your dedicated GPU
- Try adding Display Capture instead of Game Capture

### ✗ Echo / hearing yourself in headphones

- Go to `File` → `Settings` → `Audio` → set Monitoring Device to your headphones
- Check that Monitor and Output isn't accidentally selected on your mic

## Helpful Resources

- OBS Official Help: https://obsproject.com/help
- OBS Discord: https://discord.gg/obsproject
- OBS Forum: https://obsproject.com/forum
- OBS Wiki: https://obsproject.com/wiki
