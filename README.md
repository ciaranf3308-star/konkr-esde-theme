# KONKR — ES-DE theme for the AYANEO KONKR Pocket Block

Standalone ES-DE theme, 960×720 landscape, 4:3. Display name **KONKR**,
theme folder `konkr/`. Ivory paper game view, black-and-white character
art with amber accents, charcoal system view.

> **System view rebuilt 2026-11-26 — Art Book Next's structure, verbatim.**
> The old parallelogram-slice design is gone. On the Block it did not
> render at all: the carousel showed **game screenshots + giant
> system-name text** instead of the poster art (your video, ~03:13), while
> Art Book Next — the same posters, the same logos, full-screen items —
> looks clean on the same device. So KONKR's system view is now ABN's
> shape: one **full-screen 960×720 poster per system**, the carousel at
> `itemSize 1 1` / `itemScale 1` (ABN does NOT zoom), your hero logo
> centred on top, and the ES-DE helpsystem as the bottom hints bar. No
> slices, no zoom, no divider bands, no caption rail. A system with no
> poster (SNES, Android Apps, PS2, Steam, anything you add later) falls
> back cleanly to a plain charcoal tile + the Art Book Next SVG logo —
> never game art, never giant text. Hardening: the carousel `textColor` is
> `00000000` (ABN does this too), so even if a poster file ever failed to
> load, the text fallback would be invisible instead of a giant system
> name. What the engine does when art is missing was checked in the ES-DE
> 3.5 source: the game-screenshot replacement (`onDemandTextureLoad`)
> only runs for the *gamelist* carousel, never the system carousel — so
> the screenshots in your video came from the old slice design failing to
> load on the Block's ES-DE build, and the full-screen ABN-shaped art is
> the fix that matches what already works there.

## Install (Android / KONKR Pocket Block)

1. Unzip `KONKR.zip`.
2. Copy the `konkr` folder into your ES-DE themes folder, so the file lands at:
   `ES-DE/themes/konkr/capabilities.xml`
3. In ES-DE: UI Settings → Theme → **KONKR**. Restart ES-DE.
4. Game art comes from your own media library (see below) — the theme ships
   with system posters and fallback tiles only, no per-game art.

## Artwork → system mapping

Each system's poster is your supplied black-and-white illustration,
cover-fit to **960×720 full-screen** (centre crop — the full width is
kept, 12.5% trims top and bottom; GB's window is shifted up a touch so
Mario and the temple stay in frame). Opaque RGB PNGs, no alpha, no
parallelogram, no divider bands. One line per system to swap art:
replace the matching file in `konkr/systems/<name>.png`.

> Hero logo (your own generated logos — the Art Book Next ones weren't
> good enough): the selected system's logo is your generated version —
> white + orange + black, white background removed so it sits transparent
> DIRECTLY on the poster art, exactly as you made it, centred at 0.5 0.5
> (Art Book Next's logo position). NO plate behind it — the charcoal
> plate was removed 2026-11-26 because you said the logos "still have a
> horrible background I never asked for"; the plate was that background.
> Your logos' thick black outline is what makes them read on the busy
> art. Your 7: Game Boy, Game Boy Color, Game Boy Advance, Sega Genesis,
> Sega Mega Drive, Android, PlayStation (PS1). Any system without one of
> yours (PS2, Steam, Dreamcast, SNES, Android Apps, anything you add
> later) falls back to Art Book Next's white SVG logo. `maxSize`, not
> `size`, so every logo keeps its own aspect ratio and never stretches.
> Colour is untinted white, so your orange renders exactly as generated.
> Exactly ONE hero element — the overlapping-logos bug from the broken
> build cannot come back. The name wordmark that was here before is gone.
> The background posters are untouched.
> Logo scaling fix (2026-11-26): the custom logos are pre-scaled to
> 672px wide (the exact display size at 960) instead of ~2000px wide.
> They used to rely on ES-DE's `<maxSize>` to shrink them down; if the
> ES-DE on the device ignores `<maxSize>`, they rendered at native size
> and ran off the right edge of the screen — which is what your 02:40
> screenshot showed ("SEGA GENESIS" cut off at "GENI"). Now they fit
> even at native size.
> One honest catch: the thin white SVG fallback logos wash out on a busy
> poster — Dreamcast's ABN "Dreamcast" wordmark is hard to read on the
> knight poster. If you have a Dreamcast, generate a Dreamcast logo in
> your style (like the other 7) and it will read fine; PS2, Steam, SNES
> and Android Apps are unaffected because they sit on the plain charcoal
> tile. (Note 2026-11-26: there is no Dreamcast on the device, so the
> Dreamcast logo issue is moot — the knight poster is unused there.)

| System (theme name) | Poster file | What it shows |
|---|---|---|
| `gb` — Game Boy | `systems/gb.png` (was `1000017604_0`) | Full-screen collage: Mario, Wario, Kirby, Zelda, Link, Pikachu, DK, Samus, Game Boy hardware, temple, Metroids |
| `gbc` — Game Boy Color | `systems/gbc.png` (was `1000017598_1`) | Full-screen collage: Mario, Wario, Pikachu, Link with Triforce medallion and shield, Zelda, Kirby, DK, Togepi |
| `gba` — Game Boy Advance | `systems/gba.png` (was `1000017601_3`) | Full-screen collage: Mario, Wario, Sonic, Mega Man, Link with sword and bird, Samus |
| `genesis` | `systems/genesis.png` (was `1000017599_4`) | Full-screen collage: Sonic, Tails, Knuckles, Eggman, Streets of Rage — Sonic IS Genesis, corrected 2026-11-26 ("matching to the systems is not rocket science"; the knight poster was on Genesis before this) |
| `megadrive` | `systems/megadrive.png` (was `1000017603_5`) | Crazy Taxi cab, PASSI sign, gunman, robot — corrected 2026-11-26, the user said "the crazy taxi is the mage drive one" |
| `dreamcast` | `systems/dreamcast.png` (was `1000017600_2`) | Full-screen collage: armoured knight with flaming sword, mage, ninja, warriors — the 8th poster, a Sega collage; the only Sega poster left once Sonic is Genesis and Crazy Taxi is Mega Drive, so it goes on Dreamcast. No system is left blank and no poster is left spare. If you have no Dreamcast, name the system it belongs to and it moves. NOTE: Dreamcast has no custom logo (you generated 7), so it uses the thin white ABN SVG — that wordmark is hard to read on this busy poster; a Dreamcast logo in your style would fix it. |
| `android` | `systems/android.png` (was `1000017597_6`) | Android system poster (robots, gears, settings) |
| `psx` — PlayStation | `systems/psx.png` (was `1000017624_7`) | Full-screen collage: Cloud, Crash, Spyro, Lara Croft, Solid Snake, Jill, Pac-Man, memory card — sent 2026-11-26 after the Crazy Taxi candidate was corrected; before this PSX showed the plain charcoal `_default` tile |
| `snes`, `androidapps`, `ps2`, `steam`, any other system | `systems/_default.png` | Plain full-screen charcoal tile (38,37,34) + the ABN SVG logo for that system. No poster is invented for a system you didn't supply one for. |

The mapping above is my read of each poster's content — if a poster belongs
to a different system in your head, swap the two files and the theme follows.

There are no per-system theme files: the neighbour rail labels
(`konkr/gb|gbc|gba/theme.xml`) were removed 2026-11-25 because they were
hardcoded for the GB trio in isolation and were **wrong** as soon as any
other system sat next to the trio — my own capture showed GBC's right label
reading GAME BOY while the neighbour on screen was Genesis. There are no
neighbour names at all now (ABN doesn't show them either); the hero logo
is the selected-system indicator. If you want neighbour names back, they
need your real system list in alphabetical order — one line per system,
and they go stale whenever you add a system.

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

System view (rebuilt 2026-11-26, ABN-style) — all 12 test systems walked
Right from GBC and back to GBC (round trip byte-identical): Android,
Android Apps, Game Boy, Game Boy Advance, Game Boy Color, Genesis, Sega
Dreamcast, Sega Mega Drive, Sony PlayStation, Sony PlayStation 2, Super
Nintendo Entertainment System, Valve Steam. Every poster system shows its
FULL poster with exactly ONE centred hero logo and the SELECT / CHOOSE
hints pill — no game screenshots, no giant system-name text, no
overlapping logos, no black bars. The no-poster systems (SNES, Android
Apps, PS2, Steam) show the charcoal tile + their ABN SVG logo, clean.
The two systems from your broken video are fixed on capture: Mega Drive
(Crazy Taxi poster + SEGA MEGA DRIVE logo, was a Sonic game screenshot)
and Android Apps (charcoal + android apps logo, was screenshots + text).
Android (the "missing image" you flagged) shows its robot poster + android
logo. The fan tilt is the engine default 7.5° per step; at rest the
selected poster fills the screen and neighbours are covered — the tilt
shows during navigation, as in ABN.

Game view (unchanged Crystal geometry, re-verified in the same run) —
Alien 3 (GB, complete entry): marquee, description, 1993, blue star
rating, genre, players, developer, screenshot, hero cart at full size,
title + amber rule + `ACTION • 1993 • 1` meta row all follow the selection.
Scrolled through the GB list in alphabetical sort order (Alien 3 →
Mystery Game No Media → Tetris → long-title Zelda): every field updates
together. Launch + return exercised (Alien 3 launched, ES-DE returned to
the same GB selection). One-game lists verified (Pokémon Gold on GBC,
Mario & Luigi on GBA, Streets of Rage 2 on Genesis): no broken carousel,
dimmed fallback peeks top and bottom.

Edge cases: long title truncates with an ellipsis at Crystal's measured
single-line envelope (no overflow, no layout break). Missing marquee /
screenshot leaves clean empty whitespace (Crystal's explicit rule, no ghost
text). Missing physical media falls back to the per-system tile
(`media_fallbacks/<system>.png`, charcoal cart for GB/GBC/GBA, `_default`
copies for the rest).

## Deviations from the brief / approved renders

- **System view is ABN's, not the approved render's:** the slice/rail
  design (art 86%, caption rail, hints bar) is gone — it did not render on
  the Block. The poster is now 100% of the screen, the hero logo sits
  centred on it, and the hints pill sits at the bottom. This is the
  structure that demonstrably works on your device (Art Book Next).
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
  are all 672px wide on the art; the ABN SVG fallbacks (PS2, Steam, SNES,
  Android Apps, Dreamcast) vary by their own aspect. The PS2 mark is an
  outline wordmark — it renders wide and hollow, which is the real logo's
  design, not a fault. A system with neither a custom PNG nor an SVG shows
  nothing in the hero spot. The thin white SVG fallbacks wash out on a busy
  poster (Dreamcast's wordmark on the knight poster) — a custom logo in your
  style fixes that.
- **No neighbour names:** removed 2026-11-25 — the hardcoded trio labels
  were wrong once Genesis/PS2/Steam sat next to the trio (proven in
  capture: GBC's right label said GAME BOY, neighbour was Genesis). ABN
  doesn't show them either; the hero logo is the indicator.
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
  `es_systems.xml` order. The gamelist sorts by name ascending by default
  too (so the GB list runs Alien 3 → Mystery → Tetris → Zelda, not
  gamelist.xml order).
- Carousel `unfocusedItemDimming` is a **brightness** factor (1.0 = full
  bright); `unfocusedItemOpacity` defaults to 0.5. The system carousel sets
  opacity 1 / saturation 1 / dimming 1 so neighbours stay full-bright; the
  game carousel keeps Crystal's 0.45 / 0.5 / 0.55.
- The carousel's `textColor` is the fallback text colour when art fails to
  load — Art Book Next sets it transparent (`00000000`) so a missing poster
  shows nothing instead of a giant system name. KONKR's system carousel
  does the same now. (The old slice build used cream text, which is why
  the failure showed as giant text on the Block.)
- ES-DE 3.5's game-screenshot replacement (`CarouselComponent::
  onDemandTextureLoad`) is guarded to the gamelist carousel only
  (`T == FileData*`) — it cannot put game art into the system view. If the
  system view ever shows game screenshots on a device, the theme's own
  poster/default art is not loading there.
- On a keyboard, ES-DE 3.5 maps Return = A, **Backspace = B**,
  Escape = Start, Delete = X.
- Capture tooling in the local build dir (not shipped): screenshots use
  `xshot.py` (pure-Python ctypes `XGetImage`, no ImageMagick) and keys go
  via `xkey.py` (ctypes XTest) — both survive VM rebuilds that wipe
  `import`/`xdotool`. A VM replacement wipes /usr tools; reinstall with
  `sudo apt-get install -y imagemagick xdotool` once the runtime's apt
  stream releases the dpkg lock.

## Contents

- `konkr/capabilities.xml`, `konkr/theme.xml` — theme definition
- `konkr/systems/` — per-system FULL-SCREEN posters (960×720 RGB) + `_default`
  (plain charcoal tile for systems without a poster)
- `konkr/art/` — ivory paper background (`bg_paper.png`, game view),
  solid-black system background (`bg_system.png`), clipped metadata card,
  slim graphite spine rails (`art/rails/<system>.png`), amber title rule,
  stars, soft shadow, your custom hero logos (`art/hero-custom/`,
  transparent PNGs, white background removed, pre-scaled 672px wide) and
  hero logos (`art/hero-logos/`, 212 real brand SVGs from Art Book Next,
  keyed by `${system.theme}`)
- `konkr/fonts/` — DejaVu Sans / Bold, Inter Medium (from Crystal)
- `konkr/media_fallbacks/` — per-system fallback tiles for the game carousel
- `screenshots/` — native 960×720 captures (not part of the installed theme);
  `system-snes.png` is the no-poster fallback proof (charcoal + SNES logo),
  `system-megadrive.png` and `system-android.png` are the two systems from
  the broken Block video, now fixed
- A plain `<image>` path containing `${system.theme}` resolves per system:
  ES-DE builds one themed element set per system, so the hero logo swaps
  on selection change. That is how the carousel's `staticImage` works too.
- ES-DE 3.5 has **no blur** for carousel items or images (no blur property
  anywhere in the engine). Non-selected darkening is done with
  `unfocusedItemDimming` (a brightness factor: 1.0 = full bright) and
  `unfocusedItemSaturation`; opacity stays 1 so neighbours never go ghostly.
  The ABN-style system view does not dim neighbours at all (all 1.0).
