# EUB Symbol Libraries

This directory contains KiCad symbol libraries shared across EUB-series
hardware projects.

Symbol libraries are split by component role rather than by project. Existing
libraries include:

- `EUB_Connector.kicad_sym`: connectors such as USB-C, TRS MIDI, JST, and pin headers.
- `EUB_IO.kicad_sym`: user-facing input/output parts.
- `EUB_MCU.kicad_sym`: microcontrollers and closely related controller parts.
- `EUB_Mechanical.kicad_sym`: mechanical-only schematic references such as cutouts and mounting intent.
- `EUB_Module.kicad_sym`: reusable modules such as MCU modules and display modules.
- `EUB_Passive.kicad_sym`: resistors, capacitors, inductors, and similar passive parts.
- `EUB_Power.kicad_sym`: regulators, chargers, power-path parts, and power support parts.
- `EUB_Protection.kicad_sym`: ESD, fuse, and other protection parts.
- `EUB_USB.kicad_sym`: USB-specific interface parts when they are better kept separate from generic connectors.

Use upstream KiCad official symbols when they are adequate. Add EUB-maintained
symbols only when a custom pin model, simplified representation, house naming,
or project-specific mechanical intent is useful across more than one project.

See `docs/naming_conventions.md` for symbol naming rules.
