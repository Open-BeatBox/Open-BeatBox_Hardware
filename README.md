# Open-BEATBox — Hardware

CAD sources and production files for the Open-BEATBox apparatus.

## Contents

`CAD_files/` holds two hardware generations, **V2** and **V3**.

### `V2/`

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

### `V3/`

Neutral-format sources per module — `RPI_shield_V3/`, `feeder_V3/`,
`lighting_V3/`, `screen_V3/`, `tunnel_V3/` — each with a `.STEP` file, a `.zip`
archive of the native CAD project, and a `PRODUCTION/` subfolder of `.STL`
files (plus one `.DXF` under `lighting_V3/`).

Note: `screen_V3/` has no `.zip` archive; only its `.STEP` file and
`PRODUCTION/` folder are present.

`CAD_files/README.md` is an unfilled changelog template carried over from the
source repository.

## Licence

CERN Open Hardware Licence Version 2 — Strongly Reciprocal
(**CERN-OHL-S-2.0**). See [`LICENSE`](./LICENSE).

## Project links

- Project website: https://open-beatbox.github.io/
- Manual: https://open-beatbox.github.io/docs/manual/

## Issues

Please report problems with these CAD files in this repository's
[issue tracker](https://github.com/Open-BeatBox/Open-BeatBox_Hardware/issues).
