# SHIFTBOUND

A tiny two-world platformer made for **GitHub Game Off 2026** (theme: **SHIFT**).
Submission deadline: **Dec 2, 2026, 05:37 (Beijing time)** via itch.io, with the
source in a public GitHub repository.

## The game in one line

Run and jump through 3 levels, and press **SHIFT** to flip between two parallel
worlds — platforms and hazards only exist in one world at a time, so the way
forward is always in the *other* world.

## How to play

| Action | Keys |
| --- | --- |
| Move | ← → or A / D |
| Jump | ↑ or W or Z |
| Chain jump | Press jump again in mid-air — each chained jump is stronger than the last (up to 5 in a row), so any step can be climbed |
| **Shift worlds** | **Shift** or **Space** or **X** |
| Restart level | R |
| Start / restart run | Enter |

- World A is **AZURE** (blue), World B is **EMBER** (orange).
- Platforms of the inactive world are shown as faint ghosts: visible, but not solid.
- Spikes of the inactive world can't hurt you. Spikes drawn in white hurt in both worlds.
- You can't shift if your body would end up inside a platform of the other world.
- Reach the portal at the end of each level. Falling into a pit or touching spikes
  restarts the level (and adds to your death count — the win screen keeps score).

## Run it locally

No build step, no dependencies. Either open `index.html` directly in a browser, or:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Files

- `index.html` — page shell
- `style.css` — page styling
- `game.js` — the whole game (levels, physics, rendering)
- `ASSETS.md` — placeholder-art inventory: what to replace with final art, and sizes

## Status

Playable: title screen → 3 levels → win screen with time & deaths.
Final AI-generated art (dual-form hero, two world backgrounds, portal) is
integrated in `assets/`; the original Canvas shapes remain as automatic
fallback if an image fails to load. See `ASSETS.md` for details.

## AI use disclosure (draft — required by Game Off rules)

> This game was made with AI assistance: the code and placeholder art were
> produced with the help of an AI assistant, and AI tools may also be used for
> final art assets. AI use is disclosed here and in the itch.io submission
> form, as required by the Game Off 2026 rules. Game design direction, level
> selection and final decisions are the submitter's own.

（中文说明：本游戏由 AI 辅助编程与美术生成。Game Off 2026 官方明确允许使用
AI 工具，但要求提交时如实披露——提交 itch.io 时请在表单中勾选/填写 AI 使用
情况，并保留上面这段披露文字。）
