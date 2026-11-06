# ASSETS.md — placeholder art inventory

Most art started as Canvas shapes in `game.js`; each placeholder is tagged
in the code with an `ASSET:` comment at the exact draw call to replace.
Entries marked ✅ 已接入 below now load final art from `assets/` (game.js
preloads them and falls back to the Canvas placeholder if a file fails to
load). Replace the remaining ones one by one with final art; the gameplay
code (sizes, hitboxes) does not need to change if the suggested sizes are kept.

Coordinate system: playfield is 960×540. Player hitbox is 30×38 px.

## Sprites to replace

| # | Asset | Where (game.js) | Current placeholder | Suggested final size / notes |
| --- | --- | --- | --- | --- |
| 1 | Player character — World A form | `drawPlayer()` | Blue rounded square with one eye (kept as fallback) | ✅ 已接入：`assets/player_a.png` (96×110, transparent). Drawn 52px tall at native aspect, centred on and bottom-aligned with the 30×38 hitbox |
| 2 | Player character — World B form | `drawPlayer()` | Orange rounded square with one eye (kept as fallback) | ✅ 已接入：`assets/player_b.png` (91×110, transparent). Same draw treatment as #1; cloud (A) vs flame (B) reads as "the same character, shifted" |
| 3 | Platform tile — neutral (both worlds) | `drawPlatforms()` | Grey block with lighter top edge | Tileable PNG, 48×48 segment; must read clearly as solid ground |
| 4 | Platform tile — World A | `drawPlatforms()` | Azure block | Tileable PNG, 48×48; azure family |
| 5 | Platform tile — World B | `drawPlatforms()` | Ember block | Tileable PNG, 48×48; ember family |
| 6 | Ghost platform rendering | `drawPlatforms()` | Same block at 15% opacity | No new file needed — keep the alpha treatment, or supply a dedicated "ghost" variant with dashed outline |
| 7 | Spikes — world hazards | `drawSpikes()` | Triangles in world color | Tileable PNG, 30 wide × 18 high per spike |
| 8 | Spikes — neutral (both worlds) | `drawSpikes()` | White triangles | Same size as #7, neutral/white palette |
| 9 | Goal portal | `drawGoal()` | Pulsing ring + "GOAL" text (kept as fallback) | ✅ 已接入：`assets/portal.png` (95×150, transparent). Drawn 84px tall at native aspect with the original pulse scale; the "GOAL" text label is not drawn when the image is used |
| 10 | Background — World A | `drawBackground()` | Gradient + drifting circles (kept as fallback) | ✅ 已接入：`assets/bg_a.jpg` (960×540), drawn full-frame; the drifting shapes remain as a faint overlay. Parallax layers not implemented (single image) |
| 11 | Background — World B | `drawBackground()` | Gradient + drifting circles (kept as fallback) | ✅ 已接入：`assets/bg_b.jpg` (960×540), ember palette. Same treatment as #10 |
| 12 | Shift effect | `tryShift()` / `draw()` | None yet (instant flip + red X flash when denied) | Optional: a quick particle/ring burst sprite or a 6-frame flip animation; also a "shift denied" icon to replace the drawn red X |
| 13 | Title / win screens | `drawTitle()`, `drawWin()` | System-font text | Optional: a logo lockup for "SHIFTBOUND" (~600×120) and small UI icons (skull for deaths, clock for time) |

## Style direction (suggested)

- Two palettes only: azure (World A) vs ember (World B); neutral elements in grey/white.
- The shift fantasy should read instantly: when the world flips, background,
  platforms and the player all change palette in the same frame.
- Keep silhouettes chunky and readable at 960×540 — this is a precision
  platformer, so clarity beats detail.

## Audio (not yet implemented)

No sound in the prototype. If added later, keep it tiny: jump blip, shift
whoosh, death buzz, goal chime. All generatable; no files needed yet.
