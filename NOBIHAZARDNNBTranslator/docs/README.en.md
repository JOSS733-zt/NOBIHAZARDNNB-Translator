# Nobihazard NNB-Translation — User Guide

Author: JOSS · single exe · no installation

## Supported engines

| Engine | Data | Method |
|---|---|---|
| RPG Maker MV / MZ | `data\*.json` | write back, or install the runtime compare plugin |
| RPG Maker XP | `Data\*.rxdata` | direct write-back |
| RPG Maker VX | `Data\*.rvdata` | direct write-back |
| RPG Maker VX Ace | `Data\*.rvdata2` | direct write-back |

RPG Maker 2000 / 2003 (`.ldb`) is not supported.

## Three steps

1. **① Select game** — pick the folder containing `www` / `data` / `Data`, then **Detect**
2. **② Settings** — choose an engine, hit **Test engine**, then **③ check the sections**
3. **Scan text** → **Translate** → **Write back** (a backup is made first)

## Engines (all keyless)

| Engine | Notes |
|---|---|
| Microsoft (default) | `cn.bing.com`, works from mainland China; lower threads to 1 if throttled |
| MyMemory | works from mainland China, ~5000 chars/day; best at keeping `[[0]]` tokens |
| Google free | needs a proxy from mainland China |

## Sections

Only the checked sections are scanned and translated: Map events / Map names / Common events / Items / Skills / Weapons / Armors / Actors / States+Enemies / Troops / System / Other.

Unchecked rows are hidden from the table and never translated.

## Files

```
<game folder>
├── translate\cache_<lang>.json   resume cache
├── translate\glossary.txt        custom terms
├── translate\compare_*.html      source/translation report
└── translate\backup_*\           backup taken before write-back
```

MV/MZ additionally use `data\TranslatePlus\` and `js\plugins\TranslatePlus.js`.

## FAQ

- **Crashes on start** — check `startup.log` / `crash.log` next to the exe
- **Not detected** — select the folder containing `data` / `Data`; unpack `Game.rgss3a` first
- **"empty response"** — throttled; set threads to 1 and wait a few minutes
- **Status "review"** — the engine dropped a control code; edit the translation cell
- **Chinese shows as boxes** (XP/VX/VA) — replace the font in `Fonts\`
- **Rename / language** — edit `name=` / `lang=` in `nnb.ini`

## License

MIT. Free forever, no payment, no activation. The tool contains no game assets.
