# EUB KiCad Library

## Contents
- symbols
- footprints
- 3dmodels
- docs

## Usage
Register as KiCad Global Library

## Symbol Naming Convention

Format:

`<PartName>[_<Role or Variant>][_EUB]`

- **Why official part numbers are used:** Symbols are named after the manufacturer part number (MPN) to keep schematics unambiguous, searchable, and consistent across projects and BOM workflows.
- **When to add `_<Role or Variant>`:** Add a role/variant suffix only when the same base part name would otherwise collide, or when the symbol intentionally represents a specific configuration (e.g., power-path vs charger-only, pinout variant, package variant, board/module variant).
- **Why the `_EUB` suffix exists:** Use `_EUB` when a symbol is intentionally EUB-specific (custom pin naming, simplified pin set, house conventions, or non-standard metadata). This helps distinguish EUB-maintained symbols from upstream/vendor/general-purpose symbols and avoids accidental substitution.

Examples:

- `BQ24074_Charger`
- `TPS61023`
- `ESP32-S3-MINI-1_WROOMless_EUB`
- `SSD1306_Module_EUB`


## License
MIT

## Note
Work in progress
