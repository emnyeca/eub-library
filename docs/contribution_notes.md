# Contribution Notes

This repository should stay small, reusable, and reviewable. Prefer upstream
KiCad official library parts when they are adequate.

Add EUB custom parts only when one of these is true:

- The official KiCad part is missing or physically unsuitable.
- EUB needs a house variant, such as no silkscreen, panel-safe geometry, or
  explicit mechanical intent.
- The part is likely to be reused across more than one EUB project.

## Required source notes

For custom symbols or footprints, document the source used to create or verify
the part. Useful sources include:

- Manufacturer datasheet.
- Mechanical drawing.
- Vendor recommended footprint.
- Measured production sample, clearly marked as measured.
- Project-specific board requirement.

Do not add random downloaded third-party parts without checking license and
source quality.

## Footprint documentation

For custom footprints, record:

- Dimensions and units.
- Courtyard intent.
- Fabrication layer notes.
- Silkscreen policy, including `_NOSILK` variants.
- 3D model source when a model is attached.
- Verification status.

For connector footprints, also record:

- Pin numbering.
- Board orientation.
- Mating direction or cable direction when relevant.

For mechanical footprints, also record whether they affect:

- `Edge.Cuts`
- NPTH
- Keepouts
- Graphic layers
- Fabrication or assembly notes

## Verification status

Do not add unverified production footprints without marking them as unverified.

Use one of these verification labels:

- `UNVERIFIED`: created from a source, but not checked against print, order, or assembly.
- `PRINT_CHECKED`: checked on a 1:1 print or equivalent mechanical review.
- `PCB_ORDERED`: used in a board order, but assembly or fit has not been fully confirmed.
- `ASSEMBLY_TESTED`: physically assembled or fit-tested successfully.

When status changes, update the part note in the same change that records the
evidence.
