# KiCad Global Library Setup

This repository is intended to be registered as a KiCad Global Library for
personal EUB hardware development.

## Clone the repository

Clone `emnyeca/eub-library` to a stable local path, for example:

```powershell
git clone https://github.com/emnyeca/eub-library.git D:\emnye\Documents\GitHub\eub-library
```

Avoid moving the repository after KiCad libraries are registered, because KiCad
stores filesystem paths in its library tables.

## Register symbol libraries

1. Open KiCad.
2. Open `Preferences` > `Manage Symbol Libraries`.
3. Select the `Global Libraries` tab.
4. Add the required `.kicad_sym` files from `symbols/`.
5. Use stable nicknames that match the library filenames, such as `EUB_Connector`
   or `EUB_Power`.

Register only the symbol libraries that a project actually needs. Additional
libraries can be added later.

## Register footprint libraries

1. Open KiCad.
2. Open `Preferences` > `Manage Footprint Libraries`.
3. Select the `Global Libraries` tab.
4. Add the required `.pretty` directories from `footprints/`.
5. Use stable nicknames that match the directory names, such as `EUB_Connector`
   or `EUB_Mechanical`.

Each `.pretty` directory is a KiCad footprint library.

## Release-critical projects

Global library registration is convenient for personal development, but it can
make a project sensitive to future library edits.

For release-critical boards:

- Record the exact `eub-library` commit or tag used for the board.
- Prefer project-local copies for critical footprints if a board must remain
  buildable without changes from this shared repository.
- Re-run footprint, courtyard, fabrication, and 3D checks after updating the
  shared library revision.

Do not treat global registration as a substitute for release documentation.
