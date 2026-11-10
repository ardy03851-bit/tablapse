# Tablapse

A browser-based screen recorder with built-in time-lapse review. Share a tab or your whole screen, keep drawing or working in other tabs while the capture runs in the background, then replay the entire session at up to 16x speed.

Runs entirely client-side — no server, no uploads. Recordings stay in your browser's memory until you download them.

## Features

- **Tab / screen / window capture** via the Screen Capture API (`getDisplayMedia`)
- **Background capture** — recording continues while you switch tabs or apps
- **Pause / resume** mid-session
- **Time-lapse review player** — playback speeds from 0.25x to 16x, scrubbing, 5s skip, keyboard shortcuts (Space, arrows, J/K/L)
- **Audio options** — tab/system audio, microphone commentary, or both mixed
- **Frame rate** (24/30/60) and **quality** (Standard/High/Maximum) presets
- **Library** with thumbnails, duration, file size, rename, download (MP4 or WebM depending on browser), and delete

## Usage

1. Open the site in a browser that supports screen capture (Chrome, Edge, Firefox, or Safari — including Safari on iPadOS/iOS 27+).
2. Press **Start capture** and pick the tab or screen to record.
3. Switch to your drawing app or any other tab and work normally. The recording keeps running.
4. Press **Stop & save** when done. The session appears in your Library.
5. Open **Review**, pick a speed (up to 16x), and watch the time-lapse. Download to keep a copy.

## Browser support

| Browser | Capture | Notes |
| --- | --- | --- |
| Chrome / Edge (desktop) | Full | Best experience; tab audio, surface switching |
| Firefox (desktop) | Full | No tab audio |
| Safari (macOS) | Full | Records MP4 |
| Safari (iPadOS / iOS 27+) | Supported | System share picker |
| Safari / Chrome (iOS/iPadOS 26 and older) | Not available | Use the built-in Control Center screen recorder instead |

Recordings are held in memory for the browser session only — download anything you want to keep before closing the tab.

## Tech

Single self-contained `index.html` — no build step, no dependencies at runtime. Built on the Screen Capture API, MediaRecorder, and the File/Blob APIs.

## Development

```bash
# serve locally (getDisplayMedia needs a secure context — localhost works)
python3 -m http.server 8000
# open http://localhost:8000
```

## License

MIT
