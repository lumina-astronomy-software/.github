# Lumina Astronomy Software

Remote camera control for astrophotography. The app speaks one HTTP protocol, `lumina.camera.v1`; a small adapter next to the camera knows the body, the lens and the USB.

```
camera ──USB──► adapter ──HTTP + WHEP──► Star Watcher
```

## Repositories

| | |
|---|---|
| [**lumina**](https://github.com/lumina-astronomy-software/lumina) | Star Watcher: live view, exposure, capture, timelapse. Tauri v2 + SvelteKit for macOS, Windows, Linux and Android 12+. Ships with a built-in simulator, so no hardware is needed to try it. The protocol spec is in [`PROTOCOL.md`](https://github.com/lumina-astronomy-software/lumina/blob/main/packages/shared/PROTOCOL.md). |
| [**canon-adapter**](https://github.com/lumina-astronomy-software/canon-adapter) | Reference adapter for Canon DSLRs on a single-board computer: gphoto2 → ffmpeg → MediaMTX. |

## Write an adapter

Any camera can join. Implement the handshake `GET /adapter` and the routes from `PROTOCOL.md`, and Star Watcher will drive it without changes to the app.

[lumina.isamarin.xyz](https://lumina.isamarin.xyz)
