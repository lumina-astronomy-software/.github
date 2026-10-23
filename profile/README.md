# Lumina Astronomy Software

Remote camera control for astrophotography. The Lumina app speaks one HTTP protocol, `lumina.camera.v1`; a small adapter next to the camera knows the body, the lens and the USB.

```
camera ──USB──► adapter ──HTTP + WHEP──► Lumina
```

## Open repositories

| | |
|---|---|
| [**lumina**](https://github.com/lumina-astronomy-software/lumina) | The Lumina app: live view, exposure, capture, timelapse. Tauri v2 + SvelteKit for macOS, Windows, Linux and Android 12+. Ships with a built-in simulator, so no hardware is needed to try it. The protocol spec is in [`PROTOCOL.md`](https://github.com/lumina-astronomy-software/lumina/blob/main/packages/shared/PROTOCOL.md). |
| [**canon-adapter**](https://github.com/lumina-astronomy-software/canon-adapter) | Reference adapter for Canon DSLRs on a single-board computer: gphoto2 → ffmpeg → MediaMTX. |

## Write an adapter

Any camera can join. Implement the handshake `GET /adapter` and the routes from `PROTOCOL.md`, and Lumina will drive it without changes to the app.

## In the works

Not public yet:

- an agent for the board with drivers for several camera bodies;
- a phone companion that drives a DSLR over USB and shoots the wide field alongside it;
- low-poly 3D scenes of observing sites with the real sky, and a night forecast that answers "is it worth shooting tonight".

[lumina.isamarin.xyz](https://lumina.isamarin.xyz)
