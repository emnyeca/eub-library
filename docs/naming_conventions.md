# Naming Conventions

These rules extend the root `README.md` naming policy without replacing it. If
there is a conflict, keep compatibility with the existing root README.

## Symbol names

Format:

```text
<PartName>[_<Role or Variant>][_EUB]
```

Use the official manufacturer part number when applicable. This keeps
schematics searchable and keeps BOM-related names unambiguous.

Use a role or variant suffix only when it adds useful distinction, such as:

- Avoiding a collision between parts with the same base name.
- Marking a pinout, package, module, or board variant.
- Separating a role-specific representation, such as charger-only versus
  power-path use.

Use `_EUB` when the symbol is intentionally EUB-specific, such as custom pin
naming, simplified pin sets, house metadata, or non-standard schematic intent.

Examples:

- `BQ24074_Charger`
- `TPS61023`
- `ESP32-S3-MINI-1_WROOMless_EUB`
- `SSD1306_Module_EUB`

## Mechanical symbols

Format:

```text
MECH_<Purpose>[_<Variant>][_EUB]
```

Mechanical symbols describe non-electrical schematic intent such as mounting
holes, cutouts, panel windows, slots, and alignment references.

Examples:

- `MECH_MOUNT_HOLE_M2_EUB`
- `MECH_USB-C_CUTOUT_EUB`
- `MECH_OLED_WINDOW_0.96_EUB`

The physical behavior belongs in the footprint: NPTH, Edge.Cuts, keepouts,
graphics, and fabrication notes are footprint responsibilities.

## Electrical footprints

Format:

```text
<PartName>[_<Package or Variant>]_EUB
```

Use the official part name or package name when applicable. Add package or
variant information when it prevents ambiguity or records a meaningful physical
difference.

Examples:

- `TPS61023DRLR_SOT563_EUB`
- `BQ24074_QFN16_EUB`
- `MST23D18G2_DP3T_SMD_EUB`

## Mechanical footprints

Format:

```text
MECH_<Purpose>[_<Size or Variant>]_EUB
```

Mechanical footprints have no electrical meaning and normally should not appear
in BOMs. They may define NPTH, slots, Edge.Cuts, keepouts, windows, or
manufacturing references.

Examples:

- `MECH_USB-C_CUTOUT_EUB`
- `MECH_OLED_0.96_WINDOW_EUB`
- `MECH_MOUNT_HOLE_M2_NPTH_EUB`
- `MECH_SLIDEPOT_SLOT_20MM_EUB`

## Graphic footprints

Format:

```text
GFX_<Name>[_<Layer or Variant>]_EUB
```

Graphic footprints are used for visual marks on silkscreen, solder mask, or
isolated copper layers.

Examples:

- `GFX_EUB_LOGO_TOP_SILK_EUB`
- `GFX_EUB_LOGO_BOTTOM_MASK_EUB`
- `GFX_EMIUET_NAMEPLATE_TOP_EUB`
- `GFX_DECOR_PATTERN_A_CU_EUB`

Copper graphics must not be assigned to nets. They are visual material only,
usually for ENIG contrast or front-panel design.

## `_NOSILK` variants

`_NOSILK` variants are allowed when the footprint geometry is otherwise the
same but silkscreen is intentionally removed.

Use this for front-panel PCBs or other layouts where component silkscreen would
create visual clutter. Keep the rest of the name compatible with the normal
electrical or mechanical footprint rule.

## Legacy names

Older symbols and footprints may temporarily use names that do not fully match
the current naming convention.

New parts must follow the current naming convention. Existing names should not
be changed casually because KiCad projects may reference those exact symbol or
footprint names.

Rename existing parts only as a standalone cleanup task, and leave a migration
note that explains the old name, the new name, and the affected projects when
known.

This policy update does not rename existing symbols or footprints.
