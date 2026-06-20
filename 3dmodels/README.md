# EUB 3D Models

This directory is reserved for STEP, WRL, or other 3D model assets used by EUB
KiCad libraries.

Model policy:

- Prefer upstream KiCad or vendor models when licensing and accuracy are clear.
- Do not commit third-party models unless their license allows redistribution.
- Do not commit large binary assets unless they are needed for review or release work.
- Consider Git LFS before adding large or frequently changing binary models.
- Keep model paths stable once footprints reference them.

Organize models by component category when assets are added, for example
`Module/`, `Connector/`, `Switch/`, and `Mechanical/`.
