# World of Warcraft Default Interface Reference Archive

An unofficial reference archive of World of Warcraft default user interface source code and native visual assets, extracted directly from official client builds.

This package serves as a developer baseline for WoW AddOn creators, UI skinners, and tooling authors to inspect native Blizzard implementations, track API deprecations, explore frame templates and mixins, and look up texture file paths.

---

## Package Structure

- **BlizzardInterfaceCode/**
  - **Interface/AddOns/**: Default Blizzard UI tools and modular addons.
  - **Interface/FrameXML/**: Core game UI frames, action bars, and unit frame definitions.
  - **Interface/SharedXML/**: Shared utilities, widgets, mixins, and constants.
- **BlizzardInterfaceArt/**
  - Native Blizzard Picture (`.blp`) textures organized by engine directory (`Buttons/`, `FrameXML/`, `Icons/`, `Tooltips/`, etc.).

---

## Features & Developer Use Cases

- **Lua & XML Modernization:** Diff code across client flavors (Retail, Classic, PTR) to catch API deprecations, signature changes, and modern `C_*` namespace migrations.
- **Taint-Safe UI Architecture:** Reference Blizzard's native implementations of object pools (`CreateFramePool`), mixins (`CallbackRegistryMixin`), and structured layouts.
- **Original Texture Integrity:** Textures are preserved in their native `.blp` format to retain original mipmaps, alpha channels, and palette tables without conversion artifacts.
- **Asset Path Lookup:** Identify exact in-game paths to reference textures directly using `SetTexture()` or `<Texture file="..."/>`.

---

## Working with .BLP Textures

Because `.blp` files do not open natively on standard operating systems, you can view or convert them to `.png` locally using common community tools:

- **BLPNG Converter:** Simple drag-and-drop batch converter.
- **Kanma's BLPConverter:** High-speed, lightweight command-line tool.
- **Macsimka's BlpConverter:** Modern desktop UI supporting full folder hierarchy conversion and alpha channel preservation.

---

## Extraction Method

Files in this archive are generated directly from client binaries using the built-in game engine developer console:

1. Enable the console in the Battle.net App under **Game Settings > Additional command line arguments**: `-console`
2. Launch the client and toggle the engine console using the tilde key (`~`).
3. Run the export commands:
   ```text
   ExportInterfaceFiles code
   ExportInterfaceFiles art
## Legal & Copyright Disclaimer

This project is an **unofficial community reference resource** and is not affiliated with, maintained by, or endorsed by Blizzard Entertainment.

* All World of Warcraft code, XML markup, textures, icons, and visual assets are copyright © **Blizzard Entertainment, Inc.**
* World of Warcraft and Blizzard Entertainment are trademarks or registered trademarks of Blizzard Entertainment, Inc. in the U.S. and/or other countries.
* This distribution is intended exclusively for non-commercial educational, interoperability, and addon development reference purposes.
