# Project Usage Notes

Use this repository for EUB-series KiCad assets that are likely to be reused.
Keep project-specific one-off parts local to the project unless they are likely
to become shared hardware vocabulary.

## Expected project use

`emiuet-session` may reference this repository for bench footprints, module
symbols, connectors, and mechanical references used by prototype or session
hardware.

`hearth` may reference this repository for power, connector, switch, package,
and mechanical footprints that are shared with other EUB hardware work.

`changes` should normally not depend on this KiCad library repository. If
hardware documentation is later added to `changes`, only then should it
reference the relevant shared library assets.

## Shared versus project-local parts

Prefer this repository when:

- A symbol or footprint is reusable across EUB projects.
- A house convention should stay consistent.
- A mechanical or graphic pattern belongs to the EUB series rather than one
  board.

Prefer project-local libraries when:

- A part is a one-off experiment.
- The footprint is tied to a single board revision.
- The part is not yet stable enough to share.
- Release-critical reproducibility requires a frozen copy.

Do not mix final production footprints with experimental unverified footprints
without clear verification status.
