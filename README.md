# Haunted Hearts — Halloween Co-op Puzzle Game

**Some doors only open when we help each other.** Haunted Hearts is a free Halloween puzzle from Midnight Candy Club, created for [Love Game](https://love-game.org/). Guide two friendly ghosts through eight little haunted rooms, recover their half-hearts, share a lantern, and bring them safely home.

**[GitHub Pages deployment target](https://ashintop.github.io/halloween-love-game/)** · [Embedding guide](EMBEDDING.md)

**Deployment status:** GitHub Pages is not live yet. The `ashintop.github.io` links in this document are intended deployment addresses. Use the local-run instructions until the hosted game has been published and verified.

[Video player and transcript (deployment target)](https://ashintop.github.io/halloween-love-game/intro.html) · [Captioned MP4 file](docs/media/intro.mp4). The 24-second silent introduction uses actual game screenshots; it is not a live gameplay recording.

![Haunted Hearts: Luna and Rose in a Halloween puzzle room with colored heart goals, pressure gates, and a shared lantern](docs/images/gameplay.jpg)

Enjoy a little cooperative puzzle solving? **[Star this repository](https://github.com/AshinTop/halloween-love-game)** to save Haunted Hearts and follow future improvements.

## A gentle escape-room adventure for two little souls

Luna and Rose each have a half-heart to collect and a matching arch to reach. You can guide both ghosts yourself by switching the active character, or share one device and discuss or take turns making moves.

The rooms gradually add cooperative ideas. Standing on a moon or star plate holds the matching gates open. Colored tiles belong to only one ghost, so the partners may need different routes. Later, a single lantern lets its carrier enter mist; pass it when the two ghosts are adjacent so both can cross.

It is a logic puzzle about helping a partner. There is no timer, online matchmaking, chat, relationship score, or need for an account.

## Features

- **Eight single-screen rooms**, each with a complete solver-verified route.
- Two independently controlled ghosts, personal heart collectibles, and separate home arches.
- Pressure plates and matching gates, role-specific paths, mist, and one shared lantern.
- Unlimited undo and restart, room selection, and a real next-step hint from the current position.
- Local best move counts for each room, room links, and sharing based on the actual result.
- Original SVG ghost characters, illustrated scenery, synthesized sound, and a persistent mute option.
- English and Simplified Chinese, touch controls, adjacent-tile tapping, keyboard play, and reduced-motion support.
- A compact iframe layout that keeps the essential controls usable in the main site’s small game stage.
- Static HTML/CSS/ES modules with no framework, backend, CDN, installation, or external runtime assets.

## How to play

1. Choose Luna or Rose and move the active ghost.
2. Collect Luna’s blue half-heart and Rose’s pink half-heart. Each ghost collects only its own.
3. Stand on moon or star pressure plates to hold their corresponding gates open. A partner can take over a plate on the other side.
4. Respect the character-only tiles: Luna uses blue moon tiles; Rose uses pink rose tiles.
5. Pick up the lantern to enter mist. When the ghosts are next to each other, pass it to the partner who needs it.
6. Finish with both hearts collected and both ghosts on their own arches.

A ghost already standing in mist may leave it after passing the lantern away. Ghosts cannot occupy the same square. Pressure gates depend on where the characters are standing, so plan who holds the door before moving through it.

## Controls

| Action | Touch / mouse | Keyboard |
|---|---|---|
| Choose a ghost | Tap its portrait or its board character | Q switches |
| Move the active ghost | Direction buttons, or tap an adjacent square | Arrow keys / WASD |
| Pass the lantern while adjacent | **Pass the lantern** | L |
| Undo a move | **Undo** | Z |
| Find the next step | **A little hint** | Tab to the hint button |
| Restart / select a room | In-game buttons or compact room menu | Tab to a control |

The hint selects the relevant character and tells you a legal next action on a shortest route from the current state. It does not move the ghost for you. If no route exists from the current position, it recommends undoing or restarting.

## Eight rooms with a clear progression

| Room | Main idea |
|---|---|
| 1. A little spark | Find both hearts and reach the two arches |
| 2. Hold the door | Help a partner through a moon gate |
| 3. Two little favors | Coordinate moon and star mechanisms |
| 4. Different paths | Use character-specific tiles |
| 5. Share the light | Carry and pass the lantern to cross mist |
| 6. Across the hush | Combine a lantern crossing with a held gate |
| 7. Moonlit rendezvous | Leave room for a partner in a narrow passage |
| 8. Home before dawn | Bring the cooperation rules together |

The verified shortest starting routes are **8, 18, 22, 20, 19, 24, 28, and 30 moves**. Move counts provide a replay goal rather than a failure limit. You can take as many moves as you need.

## Progress, privacy, and sharing

Completed-room best move counts, language, and sound preference are stored locally. Reloading restarts the selected room instead of resuming individual unfinished moves. There is no account synchronization, so another device or a cleared browser starts with separate records.

A room link such as [`#room=6`](https://ashintop.github.io/halloween-love-game/#room=6) opens that room from its beginning. Sharing copies the real completion text and room link. It does not upload a replay or contact a social network. Clipboard restrictions fall back to visible text for manual copying.

The game code has no analytics, login, advertising SDK, remote API, or external asset requests. Guarded storage operations let play continue when storage is unavailable. Embedded and direct visits may use different storage partitions. Your hosting provider may have its own standard request logs.

## Compact-player walkthrough

![Haunted Hearts in the Love Game compact host window, with the room and persistent character and movement controls](docs/images/mobile.jpg)

Select Luna or Rose, then use the persistent direction buttons. The small-room layout keeps the active character and its moves accessible without requiring precise taps on tiny board cells. A taller host window gives the illustration more room.

*Actual interface captured in a browser iframe sized for the host player. This is a compact-window illustration, not a physical-phone test.*

## Embed Haunted Hearts

```html
<iframe
  src="https://ashintop.github.io/halloween-love-game/?embed=1"
  title="Haunted Hearts — Halloween cooperative puzzle"
  style="display:block;width:100%;height:521px;border:0"
  allow="fullscreen"
  allowfullscreen
></iframe>
```

An iframe automatically enables the compact layout. `?embed=1` forces it for a direct preview, while `?embed=0` shows the full-page presentation. `#room=1` through `#room=8` selects a room.

The main Love Game stage is approximately **833×521** on desktop and can be **356×280 or 326×280** on phones. Browser acceptance exercised those dimensions, **390×650**, and **844×340**. The first room was completed with the direction buttons at 356×280. A **480 px or taller** phone stage is more comfortable when the host can provide it; the compact 280 px mode remains available for short windows.

Board cells shrink in small stages, so use the persistent direction buttons rather than requiring precise taps on tiny tiles. Help and result dialogs scroll internally. Browser viewport checks do not claim physical-phone testing. See [EMBEDDING.md](EMBEDDING.md) for the final host sizing, permissions, and fullscreen contract.

## Local development and tests

```bash
python3 -m http.server 4173
```

Open `http://localhost:4173`. There are no dependencies or build steps. ES modules need an HTTP(S) server; a plain `file://` opening is unsuitable.

```bash
npm test
```

The Node tests verify all eight full solution routes, walls and character collisions, role-specific tiles, pressure gates, lantern passing, mist rules, and invalid room-link handling. `engine.js` holds the pure rules and breadth-first solver; `app.js` handles controls, rendering, audio, and local records.

## FAQ

### Do I need a second player?

No. You can switch characters and solve every room solo. Two people can also share the same device and plan or take turns together. The game does not connect two remote devices.

### Why can’t a ghost enter the mist?

Only the current lantern carrier can enter a mist tile. Bring the ghosts next to each other and pass the lantern when the other character needs it.

### Why did a gate close?

Moon and star gates stay open while a matching plate is occupied. Moving away can close a gate. A partner may need to hold a second plate before the first ghost leaves.

### Does a hint show the full solution?

It computes a route from the current state and displays only the next action. Undo and hints are unlimited, and neither prevents completion or a better move record.

### Is this a love calculator or compatibility test?

It is a cooperative logic game with a heart-and-ghost theme. It does not ask for names, assess relationships, or produce compatibility scores.

## More Halloween games

| Game | Another way to play |
|---|---|
| [Moonlit Mirrors](https://github.com/AshinTop/halloween-mirror-hearts) | Move two ghosts simultaneously through reflected rooms. |
| [Ghost Lanterns 3D](https://github.com/AshinTop/halloween-3d) | Solve pumpkin-light puzzles in a three-dimensional scene. |
| [Witch’s Candy Blocks](https://github.com/AshinTop/halloween-block-blast) | Fill an 8×8 candy board and brew five fixed orders. |
| [Pumpkin Jam](https://github.com/AshinTop/halloween-sprunki) | Build an original monster ensemble and try a sound-memory challenge. |

**简体中文：**《双幽灵心动逃脱》包含 8 个合作解谜房间，可单人切换角色，也可同设备两人轮流操作。帮伙伴开门、分享灯笼并收集两半爱心，支持无限撤销、真实提示与中英文切换。

## Creation credits

Designed, implemented, and reviewed through human-directed AI collaboration. The gameplay implementation, interface, and original SVG artwork were created for this project; optional sound is synthesized in the browser. Screenshots show the actual interface, and the short video is a captioned visual introduction assembled from those captures.
