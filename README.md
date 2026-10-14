# slot-nes-snes-art

NES and SNES cartridge art for [slot-nes-snes](https://github.com/felipecpaiva/slot-nes-snes),
served over GitHub Pages at https://felipecpaiva.github.io/slot-nes-snes-art/ and used by the
NES/SNES Cart Studio at https://felipecpaiva.github.io/slot-cart-studio/ .

## Layout

```
index.json                       CRC32 -> the files this set has for that dump
NES/support-texture/<CRC32>.png  the printed cartridge label (scan)
NES/wheel/<CRC32>.png            the game's clear logo
SNES/support-texture/<CRC32>.png
SNES/wheel/<CRC32>.png
```

Files are named by the CRC32 of the No-Intro dump (NES hashed whole, iNES header included; SNES
without a 512-byte copier header), so the studio looks a cart up by its checksum. An
`index.json` entry looks like:

```json
{"0021ED29": {"support-texture": "NES/support-texture/0021ED29.png", "wheel": "NES/wheel/0021ED29.png"}}
```

The set covers the dumps in one slot-nes-snes library, not every No-Intro entry. It was built
with slot-cart-studio's `tools/harvest.py` code (its ScreenScraper calls, region choice and index
format).

## Credits and licence

- Images: [ScreenScraper](https://www.screenscraper.fr/), under
  [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/). Thanks to the
  ScreenScraper team and contributors. Changes: label scans were reduced to
  256-colour palettes (dithered) to keep the set small; logos were only losslessly re-compressed.
- Game names and CRC32 checksums: [libretro-database](https://github.com/libretro/libretro-database)
  (CC BY-SA 4.0).

This set is CC BY-NC-SA 4.0 as a whole; see [LICENSE](LICENSE). Non-commercial use only.

Not affiliated with or endorsed by Nintendo. Nintendo Entertainment System, Super Nintendo
Entertainment System, NES, SNES, Famicom and Super Famicom are trademarks of Nintendo. Game names,
logos and label art are trademarks and copyrights of their respective owners.
