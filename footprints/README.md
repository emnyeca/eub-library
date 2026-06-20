# EUB Footprint Libraries

This directory contains KiCad footprint libraries shared across EUB-series
hardware projects. Each `.pretty` directory is one KiCad footprint library.

Existing library categories include:

- `EUB_Connector.pretty`: USB, audio, JST, pin header, and other connector footprints.
- `EUB_Graphic.pretty`: graphic footprints for silkscreen, mask, or isolated copper artwork.
- `EUB_IO.pretty`: user-interface and input/output footprints.
- `EUB_Mechanical.pretty`: cutouts, mounting holes, slots, keepouts, and other mechanical-only footprints.
- `EUB_Module.pretty`: reusable module footprints.
- `EUB_Package.pretty`: reusable package-level footprints for ICs and discrete parts.
- `EUB_Passive.pretty`: passive component footprints.
- `EUB_Power.pretty`: power component footprints.
- `EUB_Switch.pretty`: switch footprints.

Footprints should be added only when the official KiCad footprint is inadequate
or when an EUB-specific variant is useful. For custom footprints, document the
source, dimensions, orientation, and verification status in the footprint
metadata or an adjacent note.

See `docs/naming_conventions.md` for footprint naming rules.
