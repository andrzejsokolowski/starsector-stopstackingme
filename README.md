# StopStackingMe

A small Starsector utility mod. When you hold more than one of something, the game draws its sprite
once per unit, piled up behind the first one. This makes it draw a single sprite instead.

Covers every screen that shows cargo tiles — the cargo screen, trading, storage, loot, **and the
weapon picker in refit** — because they all share the same tile.

The quantity number in the corner, the red "you can't take this" background, tooltips and
drag-and-drop are all left exactly as they were. The only thing that changes is how many copies of
the sprite get drawn.

## Settings

Configurable through LunaLib's settings menu (`Shift+F2` in the campaign), under **Icons**:

- **Weapons - one sprite only** — on by default.
- **Crew and marines - one sprite only** — off by default. Crew and marine stacks pile up the same
  way, one extra portrait per 50 aboard.

Both apply on the next frame drawn, so you can flip one and watch the screen you're already looking
at change.

## Notes

Fighter LPCs, blueprints, AI cores, resources and special items already draw a single sprite in
vanilla, so there is nothing for the mod to do there.

When a tile holds more than one, the game nudges the front sprite down slightly to leave room for the
pile. That nudge is the game's own and stays, so a stack of three sits a few pixels lower in its cell
than a stack of one.

The refit screen inside a mission or the combat simulator runs in a different part of the game and is
not covered.

## Requirements

- [LunaLib](https://fractalsoftworks.com/forum/index.php?topic=25658.0) — settings menu
- [LazyLib](https://fractalsoftworks.com/forum/index.php?topic=5444.0) — Kotlin runtime

## Credits

`src/stopstackingme/uiframework/ReflectionUtils.kt` is Starficz's reflection utility, used unmodified
apart from its package line, and is licensed **LGPL-3.0-only**. Credits from the original: Lukas04
for his ReflectionUtils, plus Lyravega, Float and Andylizi for the original idea.
