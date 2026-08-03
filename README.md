# After the Buzzer — Horror Point & Click

A first-person horror point-and-click set in an empty arena after closing. You are
night custodial. The work order says collect every basketball in the building, and
that if the count does not match you are not to leave.

Ten sections, from the employee lockers down through the service tunnels to the main
court. Something is counting along with you.

**Play it:** https://kimberlyongwbd.github.io/After-the-Buzzer/

## Running it locally

The game is a single self-contained HTML file. There is no build step and no install.

```bash
python3 -m http.server 8420 --directory docs
```

Then open http://localhost:8420.

You can also just double-click `docs/index.html`, though serving it over HTTP is
closer to how it runs when deployed.

## Controls

| Input | Action |
| --- | --- |
| Click floor | Walk there |
| Move mouse toward screen edge | Look around |
| WASD | Walk, if you prefer |
| Click object | Collect, read, or use it |
| `F` | Flashlight (drains the battery) |
| `I` / `Tab` | Inventory |
| `J` | The James file |
| `M` / note icon (top of screen) | Mute / unmute |
| `E` | Leave a hiding place |
| `Esc` | Pause and save |

## What's in here

- `docs/index.html` — the deployed build, served by GitHub Pages
- `After the Buzzer/Afterthebuzzerindex.html` — the working source file

Both are the same file. `docs/` exists because GitHub Pages needs the entry point
named `index.html` at the root of whatever folder it serves.

## Technical notes

Everything is procedural. There are no image, audio, or model assets anywhere in the
project — textures are drawn to canvases at runtime, all sound is synthesised through
the Web Audio API, and the geometry is built in code. The only external dependency is
Three.js r128, loaded from a CDN over HTTPS.

The look is deliberately late-90s console: a low-resolution render target, vertex
snapping in a patched vertex shader, nearest-neighbour 64×64 textures, and a
post-processing chain doing VHS distortion, scanlines, chromatic aberration, grain,
and vignette.

## The James mystery

Scattered through the building are twenty-eight pieces of testimony about a player
called James, plus three defaced copies of the same team photograph. They do not
agree with each other, and that is the point — press `J` to read them side by side.
The game does not tell you who he was.
