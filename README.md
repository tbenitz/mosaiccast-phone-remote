# MosaicCast Phone Remote

A single-file multi-video viewer (main + free-moving PiP overlays **or** full-screen grid) with a **phone remote** that needs no server of your own.

## Phone remote (the important part)

The TV remote does nothing useful when you cast a Chrome tab to an Android TV / MiBox. The remote only talks to the Chromecast session, not to the JavaScript inside the page.

This version fixes that with a phone:

1. Open `index.html` in Chrome on your laptop/Chromebook.
2. The **Phone Remote** panel opens automatically and shows a short code + QR code.
3. On your phone, scan the QR (or open the same page and type the code).
4. The phone becomes the controller:
   - Play / Pause
   - Master volume
   - Per-stream volume and mute
   - Switch PiP ↔ Grid layout
   - Switch Mix ↔ Solo audio

The connection uses [PeerJS](https://peerjs.com/) (free public signaling). No Python, no local server, no accounts. Both devices need internet only for the initial handshake; after that the data channel is peer-to-peer.

### Notes
- The QR code works best when the page is hosted at an `http://` or `https://` URL (GitHub Pages, Netlify, etc.). A raw `file://` path cannot be opened by the phone via QR.
- Cast the laptop tab to your MiBox as usual. The phone is the reliable remote.
- System volume buttons on the TV remote often still control the overall cast volume.

## Features
- Main video + free-moving, resizable PiP overlays
- Optional grid layout that fills the screen with all streams
- Independent volume per source + master volume
- Mix all audio or solo the focused stream
- Local file, screen/tab share, and demo sources
- Snapshot and recording
- Works fully locally (no uploads)

## Quick start
1. Open `index.html` in Chrome.
2. Add sources with **Share tab / screen** or **Add videos**.
3. Use the phone remote (or the on-page controls).
4. Cast the tab to your Android TV if desired.

No build step. No dependencies beyond the PeerJS CDN script already included in the HTML.
