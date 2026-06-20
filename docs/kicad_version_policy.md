# KiCad Version Policy

This repository may contain KiCad library files generated or last saved with
KiCad 9.x.

KiCad 10.x migration is allowed, but it must be done as an explicit
repository-wide maintenance task. Do not casually open and save shared library
files with a different KiCad major version during unrelated part edits,
documentation work, or board-specific work.

## Board-critical work

During board-critical work, do not save shared library files with a different
KiCad major version unless that version migration is the intended maintenance
task.

Board-critical work includes:

- Preparing a PCB order.
- Implementation or assembly verification.
- Revising an existing PCB.
- Fixing a production or near-production board.

## Version migration records

When the repository moves to a new KiCad major version, record the KiCad version
in:

- The root `README.md`.
- The commit message for the version migration.

Keep the version migration separate from unrelated symbol, footprint, or board
changes so that file format churn is reviewable.

## Project reproducibility

For projects that need reproducibility before ordering boards, record the
referenced `eub-library` commit SHA or tag in the project documentation.

When a footprint is critical to a board release, copy it into a project-local
library if the project must remain buildable independently of future shared
library edits.
