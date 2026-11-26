# KONKR — ES-DE theme for the AYANEO KONKR Pocket Block

Standalone ES-DE theme, 960×720 landscape, 4:3. Display name **KONKR**,
theme folder `konkr/`. Ivory paper, black-and-white character art with amber
accents, charcoal caption rail.

## Install (Android / KONKR Pocket Block)

1. Clone or download this repo (Code → Download ZIP, or `git clone`).
2. Copy the `konkr` folder into your ES-DE themes folder, so the file lands at:
   `ES-DE/themes/konkr/capabilities.xml`
3. In ES-DE: UI Settings → Theme → **KONKR**. Restart ES-DE.
4. Game art comes from your own media library (see below) — the theme ships
   with system posters and fallback tiles only, no per-game art.

## Artwork → system mapping

System posters are your supplied black-and-white illustrations, shown
**whole — no zoom, no strip crop**. Each poster is fitted to the slice
(708×619, 1× the on-screen item box) and mounted sharp on a blurred bleed
of itself, inside the 12° parallelogram. The only crop is the slanted
divider trimming the poster's top-left and bottom-right corners. One line
per system to swap art: replace the matching file in
`konkr/systems/<name>.png`.

> Carousel rule (changed 2026-11-26 — you asked for Art Book Next with a
> zoom on the selected): the carousel now runs at `itemScale=1.4`, so the
> selected console scales up 40% as it is selected and the old one scales
> back down. The selected still draws at 708x619 and reveals the same
> 576px (60%), never cropped; the neighbours draw at 506x442 (71% of the
> selected), so they read clearly but the selected dominates. Honest note:
> Art Book Next itself sets `itemScale 1` — it does NOT zoom; its selected
> only looks big because it is fully visible and centred while neighbours
> are clipped, plus the fan tilt. The zoom here is KONKR's own. The 2026-11-25
> uniform-scale build (`itemScale=1`) made everything the same size and
> the selected only dominated by revealing more sideways. The first build
> used `itemScale=3`, so the selected drew at 3× and neighbours at 1×, and
> the non-selected art looked small. 1.4 is the middle: a real zoom,
> neighbours still readable.

> Hero logo (changed 2026-11-26 — your own generated logos, the Art Book
> Next ones weren't good enough): the selected system's logo is your
> generated version — white + orange + black, white background removed so
> it sits transparent DIRECTLY on the poster art, exactly as you made it.
> NO plate behind it any more — the charcoal plate was removed 2026-11-26
> because you said the logos "still have a horrible background I never
> asked for"; the plate was that background. Art Book Next puts its logo
> straight on the art, and so does KONKR now — your logos' thick black
> outline is what makes them read on the busy art. Your 7: Game Boy, Game
> Boy Color, Game Boy Advance, Sega Genesis, Sega Mega Drive, Android,
> PlayStation (PS1). Any system without one of yours (PS2, Steam, Dreamcast,
> anything you add later) falls back to Art Book Next's white SVG logo.
> `maxSize`, not `size`, so every logo keeps its own aspect ratio and never
> stretches. Colour is untinted white, so your orange renders exactly as
> generated. The background posters are untouched. The name wordmark that
> was here before is gone. One honest catch: the thin white SVG fallback
> logos wash out on a busy poster — Dreamcast's ABN "Dreamcast" wordmark is
> hard to read on the knight poster. If you have a Dreamcast, generate a
> Dreamcast logo in your style (like the other 7) and it will read fine;
> PS2 and Steam are unaffected because they sit on the plain charcoal tile.
> (Note 2026-11-26: there is no Dreamcast on the device, so the Dreamcast
> logo issue is moot — the knight poster is unused there.)
> Logo scaling fix (2026-11-26): the custom logos are now pre-scaled to
> 672px wide (the exact display size at 960) instead of ~2000px wide. They
> used to rely on ES-DE's `<maxSize>` to shrink them down; if the ES-DE on
> the device ignores `<maxSize>`, they rendered at native size and ran off
> the right edge of the screen — which is what your 02:40 screenshot showed
> ("SEGA GENESIS" cut off at "GENI"). Now they fit even at native size.

> Thick dividers (2026-11-25, your call: the posters are so similar the
> borders needed to be much more defined; corrected 2026-11-26 — the band
> was only on the right edge and cream, you wanted both edges and black):
> each slice's BOTH slanted edges carry a filled **24px black band** — 2px
> vanished, 10px still read thin on the Block, 24px reads as a proper
> divider, and now the left border is as thick as the right. Non-selected
> consoles also recede a touch now (unfocused dimming/saturation 0.85 —
> 15% darker, 15% less colour). ES-DE has no blur for carousel items, so
> that darkening + desaturation is the engine's version of it; the blur
> itself isn't possible in-engine.

| System (theme name) | Poster file | What it shows |
|---|---|---|
| `gb` — Game Boy | `systems/gb.png` (was `1000017604_0`) | Whole collage: Mario, Wario, Kirby, Zelda, Link, Pikachu, starters, DK, Samus, Game Boy hardware, temple, Metroids |
| `gbc` — Game Boy Color | `systems/gbc.png` (was `1000017598_1`) | Whole collage: Mario, Wario, Pikachu, Link with Triforce medallion and shield, Zelda, Kirby, DK, Togepi |
| `gba` — Game Boy Advance | `systems/gba.png` (was `1000017601_3`) | Whole collage: Mario, Wario, Sonic, Mega Man, Link with sword and bird, Samus |
| `genesis` | `systems/genesis.png` (was `1000017599_4`) | Whole collage: Sonic, Tails, Knuckles, Eggman, Streets of Rage — Sonic IS Genesis, corrected 2026-11-26 ("matching to the systems is not rocket science"; the knight poster was on Genesis before this) |
| `megadrive` | `systems/megadrive.png` (was `1000017603_5`) | Crazy Taxi cab, PASSI sign, gunman, robot — corrected 2026-11-26, the user said "the crazy taxi is the mage drive one" |
| `dreamcast` | `systems/dreamcast.png` (was `1000017600_2`) | Whole collage: armoured knight with flaming sword, mage, ninja, warriors — the 8th poster, a Sega collage; the only Sega poster left once Sonic is Genesis and Crazy Taxi is Mega Drive, so it goes on Dreamcast. No system is left blank and no poster is left spare. If you have no Dreamcast, name the system it belongs to and it moves. NOTE: Dreamcast has no custom logo (you generated 7), so it uses the thin white ABN SVG — that wordmark is hard to read on this busy poster; a Dreamcast logo in your style would fix it. |
| `android` | `systems/android.png` (was `1000017597_6`) | Android system poster |
| `psx` — PlayStation | `systems/psx.png` (was `1000017624_7`) | Whole collage: Cloud, Crash, Spyro, Lara Croft, Solid Snake, Jill, Pac-Man, memory card — sent 2026-11-26 after the Crazy Taxi candidate was corrected; before this PSX showed the plain charcoal `_default` tile |
| any other system | `systems/_default.png` | Charcoal tile with amber edges |

The mapping above is my read of each poster's content — if a poster belongs
to a different system in your head, swap the two files and the theme follows.

There are no per-system theme files any more: the neighbour rail labels
(`konkr/gb|gbc|gba/theme.xml`) were removed 2026-11-25 because they were
hardcoded for the GB trio in isolation and were **wrong** as soon as any
other system sat next to the trio — my own capture showed GBC's right label
reading GAME BOY while the neighbour on screen was Genesis. The art peeks
show the neighbours; the hero shows the selected name. If you want neighbour
names back, they need your real system list in alphabetical order — one line
per system, and they go stale whenever you add a system.

## How game art is matched (read this — it is not the gamelist)

ES-DE 3.5 finds game media **by ROM filename stem** in the configured
game-media directory, not from `<image>` / `<marquee>` / `<boxart>` tags in
`gamelist.xml` (those tags are ignored by the parser in 3.5). Verified
against the ES-DE 3.5 source (`FileData::getMediafilePath`):

```
ES-DE/downloaded_media/<system>/screenshots/<ROM stem>.png   (or .jpg/.webp)
ES-DE/downloaded_media/<system>/marquees/<ROM stem>.png
ES-DE/downloaded_media/<system>/physicalmedia/<ROM stem>.png  (carts, discs)
ES-DE/downloaded_media/<system>/3dboxes/<ROM stem>.png        (fallback after physicalmedia)
ES-DE/downloaded_media/<system>/covers/<ROM stem>.png
ES-DE/downloaded_media/<system>/videos/<ROM stem>.mp4
```

`<ROM stem>` is the ROM filename without its extension, **including** any
parenthesised parts, exactly as the file sits on disk — e.g.
`Alien 3 (1993)(Acclaim).png`, not `Alien 3.png`. Matching is case-sensitive
on Linux/Android. Relative subfolders under the ROM folder are preserved
under the media folder too.

The carousel shows `physicalmedia` first, then `3dbox`. The screenshot slot
shows miximage → screenshot → titlescreen → cover, in that order. The video
slot shows the screenshot for 5 seconds, then the video if one exists.

## What was tested (ES-DE 3.5.0 r52, Linux x86_64 AppImage, Xvfb, 960×720)

Zero theme errors in the log (`Finished loading theme "konkr"`). Screenshots
in `screenshots/` are native 960×720 captures from that run.

System view — GBC centered on launch; moves verified in both directions
across GB, GBA, GBC, Genesis, Dreamcast, Mega Drive, PSX, PS2 and Steam:
artwork, wider slice, hero logo and active system move together in every
direction, and the logo swaps per system (GBC's GAME BOY COLOR mark,
Genesis, the PS2 outline, the Steam circle + STEAM — all real logos, white,
directly on the art with no plate behind them). Dividers parallel at
~12°, now a 24px black band on both edges. Selected slice 60% of screen width at
mid-height. Non-selected consoles sit 15% darker and less saturated.
Neighbour names no longer appear on the rail (removed — see Deviations);
the hero logo is the selected-system indicator. A opens each system, B
returns to the same selection. A Genesis probe (no per-system theme file)
renders from the root theme with poster, hero and clean rail.
Uniform
scale re-verified 2026-11-25 after the `itemScale=1` fix: in the GBC, GBA
and Genesis captures the neighbours' characters are the same size as the
selected's — the neighbours only show a narrower 192px window into the same
art, and the selected dominates by revealing 576px. Whole-poster slices
re-verified at the same time: each centre slice shows the full poster (only
the slant trims the corners).

Game view — Alien 3 (GB, complete entry): marquee, description, 1993, 3.5
amber stars, genre, players, developer, screenshot, hero cart at full size,
title + amber rule + `ACTION • 1993 • 1` meta row all follow the selection.
Scrolled to three more games (missing-media, Tetris, long-title): every field
updates together. Launch + return exercised (Alien 3 launched, ES-DE
returned to the same GB selection). One-game lists verified (Pokémon Gold on
GBC, Mario & Luigi on GBA): no broken carousel, dimmed fallback peeks top
and bottom.

Edge cases: long title truncates with an ellipsis at Crystal's measured
single-line envelope (no overflow, no layout break). Missing marquee /
screenshot leaves clean empty whitespace (Crystal's explicit rule, no ghost
text). Missing physical media falls back to the per-system tile
(`media_fallbacks/<system>.png`, charcoal cart for GB/GBC/GBA, `_default`
copies for the rest).

## Deviations from the brief / approved renders

- **Metadata card width:** Crystal's 352 px card kept verbatim per "carry
  over its positions" — wider than the ~270 px card in the game-picker
  render. Crystal's text column needs the width; shrinking it would have
  reflowed every field.
- **Help labels:** ES-DE renders the left/right hint as "CHOOSE", not
  "Browse" as in the system render — that is ES-DE's built-in label, the
  theme cannot rename it.
- **Hero logo size varies by mark:** the logo fits a 672×180 box directly
  on the art (no plate — removed 2026-11-26), so wide marks render 672px wide
  and taller marks (PlayStation) render up to 173px tall. Your custom PNGs
  are all 672px wide on the art; the ABN SVG fallbacks (PS2, Steam, Dreamcast)
  vary by their own aspect. The PS2 mark is an outline wordmark — it renders
  wide and hollow, which is the real logo's design, not a fault. A system
  with neither a custom PNG nor an SVG shows nothing in the hero spot. The
  thin white SVG fallbacks wash out on a busy poster (Dreamcast's wordmark
  on the knight poster) — a custom logo in your style fixes that.
- **No neighbour names on the rail:** removed 2026-11-25 — the hardcoded
  trio labels were wrong once Genesis/PS2/Steam sat next to the trio (proven
  in capture: GBC's right label said GAME BOY, neighbour was Genesis). The
  rail is plain dark + hints; the art peeks show the neighbours.
- **Art/rail split:** art is the top 86%, rail 86–93%, hints bar 93–100%,
  per the brief. Measured on the supplied system render, the rail also starts
  at 0.86 — brief and render agree.
- **Video takeover after 5 s** is wired exactly as Crystal ships it
  (screenshot first, `<delay>5</delay>`), but no video files were in the test
  set, so the actual fade to video is unverified.
- **Round disc:** verified for a wide GB cartridge (native aspect preserved,
  large in full colour). No round-disc media was in the test set, so a real
  disc (PSX etc.) was not captured — the carousel preserves native aspect,
  so it will render round, but that is unproven on screen.
- **Not verified on the Block itself.** Tested on ES-DE 3.5.0 Linux; the
  Block's ES-DE build/version may differ. If its ES-DE predates 3.5, the
  `<metadata>` / `<systemdata>` bindings still apply (they are the 2.0+
  mechanism); if it is older than 2.0 the theme will not load.

## Notes for future edits (things that cost a day to learn)

- ES-DE 3.5 rejects `<formatVersion>` outright (the tag was removed), rejects
  the `extra="true"` attribute on `<image>` (Crystal uses it; 3.5.0 does not
  accept it), and rejects `zIndex` on `<helpsystem>`. Any of these aborts the
  whole theme file parse — one bad element kills the entire view.
- Game metadata binds via `<metadata>name|description|genre|players|
  developer</metadata>`, dates via `<datetime><metadata>releasedate</metadata>
  <format>%Y</format></datetime>`, the system name via
  `<systemdata>fullname</systemdata>`. `${game.*}` and `${system.fullName}`
  resolve to empty at load time and abort the parse.
- ES-DE sorts the system carousel alphabetically by full name, not by
  `es_systems.xml` order.
- Carousel `unfocusedItemDimming` is a **brightness** factor (1.0 = full
  bright); `unfocusedItemOpacity` defaults to 0.5. The system carousel sets
  opacity 1 / saturation 1 / dimming 1 so neighbours stay full-bright like
  the render; the game carousel keeps Crystal's 0.45 / 0.5 / 0.55.
- On a keyboard, ES-DE 3.5 maps Return = A, **Backspace = B**,
  Escape = Start, Delete = X.

## Contents

- `konkr/capabilities.xml`, `konkr/theme.xml` — theme definition
- `konkr/systems/` — per-system parallelogram posters (+ `_default`)
- `konkr/art/` — ivory paper background, caption rail, bottom bar, clipped
  metadata card, slim graphite spine rails (`art/rails/<system>.png`),
  amber title rule, amber stars, soft shadow, your custom hero logos
  (`art/hero-custom/`, transparent PNGs, white background removed) and hero
  logos (`art/hero-logos/`, 212 real brand SVGs from Art Book Next, keyed by
  `${system.theme}`)
- `konkr/fonts/` — DejaVu Sans / Bold, Inter Medium (from Crystal)
- `konkr/media_fallbacks/` — per-system fallback tiles for the game carousel
- `screenshots/` — native 960×720 captures (not part of the installed theme);
  `system-steam.png` is the Steam hero, the shot that matches your Block
  photo of Art Book Next
- A plain `<image>` path containing `${system.theme}` resolves per system:
  ES-DE builds one themed element set per system, so the hero logo swaps
  on selection change. That is how the carousel's `staticImage` works too.
- ES-DE 3.5 has **no blur** for carousel items or images (no blur property
  anywhere in the engine). Non-selected darkening is done with
  `unfocusedItemDimming` (a brightness factor: 1.0 = full bright) and
  `unfocusedItemSaturation`; opacity stays 1 so neighbours never go ghostly.
