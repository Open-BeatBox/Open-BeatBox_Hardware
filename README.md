# Open-BEATBox — Hardware

CAD sources, electronics designs and production files for the Open-BEATBox
apparatus.

## Contents

- `mechanical/` — 3D models and production files (3D printing, laser cutting) for the enclosure and modules, two hardware generations, **V2** and **V3**.
- `electronics/` — KiCad circuit-board designs and manufacturing files for the V3 modules.

## `mechanical/`

### `mechanical/V2/`

SolidWorks sources (`.SLDPRT` parts, `.SLDASM` assemblies), reference renders
(`.png`) and one drawing (`cage_1feeder_2screens.pdf`), organised per module:

| Folder | Module |
| --- | --- |
| `baseCage/` | base cage |
| `cage_1feeder_2screens/` | cage assembly with one feeder and two screens |
| `camera/` | camera and NeoPixel ring support |
| `feeder/` | feeder part and assembly |
| `passage/` | passage |
| `screen/` | screen frame |

Each module has a `production/` subfolder with the files sent to manufacturing:
`.STL` meshes for 3D printing, `.DXF` outlines for laser cutting (the filenames
carry the intended material and thickness, e.g. `..._3mm_clear.DXF`), and
sliced `.gcode` whose filenames indicate a Creality K1 Max, 0.4 mm nozzle and
Hyper PLA.

### `mechanical/V3/`

Neutral-format sources per module — `feeder/`, `lighting/`, `main/` (Raspberry
Pi shield), `screen/`, `tunnel/` — each with a `.STEP` file, a `.zip` archive
of the native CAD project, and a `PRODUCTION/` subfolder of `.STL` files (plus
one `.DXF` under `lighting/`). Alongside the modules:

| Folder | Contents |
| --- | --- |
| `enclosure/` | 3 mm wall, door and ceiling panels and the 10 mm base plate as `.DXF` for laser cutting, plus the door knob `.STL` |
| `structure/` | base plate `.DXF` and pillar `.STL` |
| `final_assembly/` | `.zip` archive of the complete assembly |

`mechanical/README.md` is an unfilled changelog template carried over from the
source repository.

## `electronics/`

One KiCad project per PCB (`BB_RPI_shield_V1`, `BB_feeder_main_V1`,
`BB_feeder_IRBarrier_V1`, `BB_lighting_V1`, `BB_screen_main_V1`,
`BB_IR_light_curtain_V2_38k`, `BB_tunnel_V1`, `BB_nosepoke_V1`), each with its
schematic exported to PDF and a `production/` folder holding the Gerber `.zip`,
BOM, pick-and-place files and IPC netlist. `STEPs/` has 3D models of the
boards and `pictures/` has renders. See
[`electronics/README.md`](./electronics/README.md) for what each board does.

## Large files

`.zip` and `.STEP` files are stored with [Git LFS](https://git-lfs.com/).
Install it before cloning (`git lfs install`), or those files will arrive as
small pointer files.

## History

`mechanical/V3/` and `electronics/` were imported with their full commit history
from the ICM GitLab project `icm-institute/rnd/projects/burguiere_beatbox_website`
(`02_CAD_files/V3` and `03_ECAD_files` on its `main` branch). They were later
renamed from `CAD_files/` and `ECAD_files/`; use `git log --follow <file>` to
see a file's history across the renames.

## Licence

CERN Open Hardware Licence Version 2 — Strongly Reciprocal
(**CERN-OHL-S-2.0**). See [`LICENSE`](./LICENSE).

## Project links

- Project website: https://open-beatbox.github.io/
- Manual: https://open-beatbox.github.io/docs/manual/

## Issues

Please report problems with these CAD and electronics files in this repository's
[issue tracker](https://github.com/Open-BeatBox/Open-BeatBox_Hardware/issues).
