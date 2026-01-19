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

## Mechanical / Cutout Symbols

This library also includes mechanical-only symbols used for PCB-based plates,
mounting holes, cutouts, and alignment references.

These symbols:
- Do not represent electrical components
- Are not intended to appear in BOMs
- Exist to document mechanical intent at the schematic level

Naming format:

`MECH_<Purpose>[_<Variant>][_EUB]`

Examples:
- `MECH_MOUNT_HOLE_M2_EUB`
- `MECH_USB-C_CUTOUT_EUB`
- `MECH_OLED_WINDOW_0.96_EUB`

All electrical behavior is defined in the corresponding footprints
(e.g. NPTH, Edge.Cuts, keepouts).

## Footprint Naming Convention

Footprints in this library are divided into two categories:
- **Electrical footprints** (for actual electronic components)
- **Mechanical-only footprints** (cutouts, mounting holes, windows, slots, etc.)

### Electrical footprints

Naming format:

`<PartName>[_<Package or Variant>]_EUB`

- **PartName:** Uses the official part number when applicable.
- **Package / Variant:** Added only when needed for clarity (to avoid collisions or to capture a meaningful package/variant distinction).
- **`_EUB` suffix:** Indicates the footprint is owned/maintained by the EUB library (to avoid accidental substitution with similarly-named upstream footprints).

Examples:
- `TPS61023DRLR_SOT563_EUB`
- `BQ24074_QFN16_EUB`
- `MST23D18G2_DP3T_SMD_EUB`

#### `_NOSILK` variants

Some footprints include `_NOSILK` variants. These variants are physically identical
to their standard counterparts, except for the absence of silkscreen graphics.

This is intentionally used to reduce layout management overhead for front-panel
style PCBs, where component silkscreen is undesired.

### Mechanical footprints

Naming format:

`MECH_<Purpose>[_<Size or Variant>]_EUB`

- These footprints have no electrical meaning.
- They are not intended to appear in BOMs.
- They usually contain NPTH, slots, Edge.Cuts, or graphical references only.

Examples:
- `MECH_USB-C_CUTOUT_EUB`
- `MECH_OLED_0.96_WINDOW_EUB`
- `MECH_MOUNT_HOLE_M2_NPTH_EUB`
- `MECH_SLIDEPOT_SLOT_20MM_EUB`

Note on responsibility separation:
- Symbols describe logical or mechanical intent.
- Footprints define physical geometry and manufacturing constraints.

### Graphic footprints (silk/mask/copper art)

Naming format:

`GFX_<Name>[_<Layer or Variant>]_EUB`

Examples:
- `GFX_EUB_LOGO_TOP_SILK_EUB`
- `GFX_EUB_LOGO_BOTTOM_MASK_EUB`
- `GFX_EMIUET_NAMEPLATE_TOP_EUB`
- `GFX_WARNING_TEXT_BATT_EUB`
- `GFX_DECOR_PATTERN_A_EUB`

Notes:
- The `GFX_` prefix is required.
- Prefer intent/meaning over exact dimensions (size should be defined by the footprint geometry itself).

### Use of Copper Layers for Graphic Design

In the EUB series, PCB copper layers (F.Cu / B.Cu) may be intentionally used
for visual and design purposes, especially for front-panel style PCBs
finished with ENIG.

These copper graphics:
- Do not represent electrical connections
- Must not be assigned to any net
- Are used purely as visual material (gold finish, contrast, texture)

Such usage is limited to dedicated graphic footprints located in
`EUB_Graphic.pretty`, and their intent must be clearly indicated in the
footprint name (e.g. `*_CU_EUB`).


## License
MIT

## Note
Work in progress
