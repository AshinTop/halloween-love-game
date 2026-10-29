# Embedding Haunted Hearts

Haunted Hearts is a static HTML/CSS/ES-module game with no build step, remote assets, or server API. Deploy the repository files together over HTTP(S); JavaScript modules do not support running this project directly from `file://`.

## Integration

```html
<iframe
  src="https://halloween-love-game.crazy3d.org/?embed=1"
  title="Haunted Hearts"
  width="100%"
  height="521"
  scrolling="no"
  allow="fullscreen"
  allowfullscreen
  sandbox="allow-scripts allow-same-origin allow-forms allow-pointer-lock allow-orientation-lock allow-presentation"
  style="display:block;width:100%;height:100%;border:0"
></iframe>
```

The example uses the live Cloudflare game URL. The sandbox value matches the existing Love GamePlayer external stage. Fullscreen is an optional capability; the host can keep its existing fullscreen button or grant the iframe permission as shown above.

The game automatically detects an iframe and enables its compact layout. `?embed=1` forces the same layout for a direct preview; `?embed=0` disables it for debugging. `#room=1` through `#room=8` selects a room; for example, `index.html?embed=1#room=6`.

## Existing host dimensions

The Love host’s desktop shell is at most 1184 px wide, with a 2.6:1 detail grid and a 28 px gap. Its main game viewport is approximately **833 × 521** at a 16:10 aspect ratio. Below 800 px the host uses one column. Below 600 px the shell width is `calc(100% - 32px)` and the game stage uses a 4:3 aspect ratio with a 280 px minimum height. This gives approximately **356 × 280** on a 390 px phone and **326 × 280** on a 360 px phone.

The game supports those compact windows without scrolling the iframe document:

- Desktop: board on the left, character selection and directional controls on the right.
- Tall phone: board above a compact strip containing the two characters, lamp action, and direction pad.
- Short landscape: smaller side controls leave the board its available height.
- Phone windows at or below 360 px high: a single-row toolbar keeps room selection, moves, undo, restart, hint, help, sound, language, and fullscreen. A fixed 43 px bottom strip keeps the two character buttons, four directional buttons, and conditional lantern-pass button accessible. The board takes the remaining space.

A `ResizeObserver` sizes the grid from the real remaining width and height and preserves each room’s proportions. The movement controls remain usable even when the board’s cells are small. Long instructions move into the help dialog; help and result dialogs can scroll internally.

Browser acceptance checked **356 × 280, 326 × 280, 390 × 650, 844 × 340, and 833 × 521**, plus the host’s expanded fullscreen view, with no document overflow or cropped essential controls. Room 1 was completed in its verified eight moves using the direction buttons at 356 × 280.

## Recommended new-game presentation

The current 280 px phone stage is playable. For more comfortable board details and dialogue, give this new game a **480 px minimum height** on phones or use the host’s fullscreen view. A dedicated class keeps this sizing decision local to this game:

```css
.external-stage.haunted-hearts {
  aspect-ratio: 16 / 10;
}
@media (max-width: 600px) {
  .external-stage.haunted-hearts {
    aspect-ratio: auto;
    height: min(650px, calc(100dvh - 80px));
    min-height: 480px;
  }
}
.external-stage.haunted-hearts iframe {
  display: block;
  width: 100%;
  height: 100%;
  border: 0;
}
```

The 80 px allowance is an integration example: replace it with the height of the actual host controls. On very short screens, use the existing compact stage or fullscreen instead of imposing the 480 px minimum. The game does not modify its parent, request a particular height via messaging, or require parent-page scrolling.

## Controls, storage, and permissions

- Keyboard: arrows / WASD move, Q switches ghosts, Z undoes, L passes the lantern when adjacent. Touch/mouse: select a ghost, then use the direction buttons or tap an adjacent tile. The iframe must have focus for keyboard input. This is cooperative play on one device, without network synchronization.
- Help, unlimited undo, restart, and a real next-move hint remain available in compact mode. Hints solve the current board state, not just a canned opening.
- Web Audio starts after user interaction and can be muted. It needs no autoplay permission.
- The iframe’s fullscreen button is disabled if the browser reports no fullscreen capability. Otherwise the host must grant fullscreen permission; the host’s own fullscreen control also works.
- Result sharing copies real text and a room link. If clipboard access is denied, the game displays them for manual copying. There is no external sharing request.
- Best moves for completed rooms, language, and mute preference use local storage. Storage restrictions or origin partitioning may prevent persistence; play continues through guarded storage operations. A room link selects its room after reload; an in-progress room restarts rather than resuming its individual moves.
- No parent DOM access, initialization messages, accounts, analytics, remote scripts, or backend are required. Keep `allow-scripts` for gameplay and `allow-same-origin` for normal origin storage behavior where the browser permits it.

All eight rooms have complete solver-verified paths, and the unit tests exercise collisions, role-specific paths, pressure gates, lantern passing, and fog. Production host QA should include its own toolbar, orientation changes, and permission policy.
