# XP / VX / VX Ace Guide

## Differences from MV/MZ

- No runtime compare plugin — **direct write-back only**
- Data format is Ruby Marshal: `.rxdata` / `.rvdata` / `.rvdata2`
- Backups go to `translate\backup_<timestamp>\Data\`

## Three steps

1. Select the folder containing `Data` → **Detect**
2. **Scan text** → **Translate**
3. **Write back**: backup first, then file by file; each file is re-parsed as a check

## What gets translated

Event dialogue, choices, scroll text, event names, map names, actors (name/nickname/description), classes, items, weapons, armors, skills, states, enemies, common events, troops, system terms and messages.

## Notes

- **Chinese shows as boxes**: the game's font in `Fonts\` has no Chinese glyphs — replace it
- **0 entries scanned**: text lives in RGSS scripts, or data is packed in `Game.rgss3a` / `.rgss2a` / `.rgssad` (unpack first)
- **Game errors after write-back**: use **Restore backup**, then send me the error
- Write-back only replaces strings and their length prefixes; every other byte is kept
