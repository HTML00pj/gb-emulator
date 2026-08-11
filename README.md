# GB Emulator

A Game Boy / Game Boy Color emulator built from scratch in JavaScript, packaged as a desktop app with Electron.

This project doesn't include or distribute any copyrighted game ROMs — you'll need to provide your own.

## Features

- Full CPU emulation (Sharp LR35902) — all documented opcodes, interrupts, timing
- PPU (graphics): background, window, and sprite rendering with proper priority handling
- Timer and Joypad emulation
- Sound (APU) — all four channels
- Cartridge support: **MBC1, MBC2, MBC3 (with real-time clock), and MBC5** — covers the large majority of commercial Game Boy and Game Boy Color games
- Battery-backed save persistence (auto-saves, survives closing and reopening the app)
- **Full Game Boy Color support**: real color palettes, extra VRAM/WRAM banking, double-speed CPU mode, and automatic hardware detection per game
- **GBC-style auto-colorization** for original (non-color) Game Boy games — games like Pokémon Red get a colorized look even though they were never CGB titles, similar to how real Game Boy Color hardware colorizes old cartridges
- Library-style interface: drag and drop a ROM to add it to your game library, click to play

## Screenshots

*(add a screenshot or two here once you have some — right-click → "Copy image" from the running app, or use Windows' Snipping Tool)*

## Getting started

You'll need [Node.js](https://nodejs.org) installed (the LTS version).

```bash
npm install
npm start
```

This opens the emulator in its own window. Drag and drop a `.gb` or `.gbc` ROM onto the Library tab (or click it to browse for a file) — it'll load straight into the Emulator tab and start playing.

## Controls

| Game Boy | Keyboard |
|---|---|
| D-pad | Arrow keys |
| A | Z |
| B | X |
| Start | Enter |
| Select | Shift |

## Known limitations

- A handful of Game Boy Color games use a hardware feature (mid-scanline HDMA) for specific screen-split color effects — that exact effect isn't reproduced, though everything else about those games works normally
- The `STOP` instruction's real "halt until button press" behavior is simplified outside of its main real-world use case (CGB speed switching)

## Built with

JavaScript, [Electron](https://www.electronjs.org/), HTML5 Canvas.

## License

MIT — see [LICENSE](LICENSE).
