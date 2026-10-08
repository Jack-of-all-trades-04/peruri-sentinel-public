# PERURI-SENTINEL Diagrams

Four architecture figures. Each one has an editable source and exports in PDF, PNG and SVG.

| Figure | Source (edit this) | Exports | Shows |
|---|---|---|---|
| 1 | `diagram_1_arsitektur_sistem.drawio` | `.pdf`, `.png`, `.svg` | System overview: HPS, FPGA fabric, demo board |
| 2 | `diagram_2_datapath_clock_domain.drawio` | `.pdf`, `.png`, `.svg` | Datapath and the two clock domains |
| 3 | `diagram_3_fsm_respon_bertingkat.drawio` | `.pdf`, `.png`, `.svg` | Response state machine (per operation and persistent tamper level) |
| 4 | `diagram_4_timing_output_release_gate.json5` | `.pdf`, `.png`, `.svg` | Cycle timing of the output release gate (clean operation and a glitch on the last round) |

## Conventions

- Lines of the same colour carry the same kind of signal: orange for the fast TDL path (no CDC), blue for slow alarms and signals that cross clock domains, red for asynchronous zeroize, green for released ciphertext.
- Blocks drawn with dashed outlines exist only in the demo build.
- Latencies and cycle counts are labelled "(target)" or "(estimasi)" until measured.

## Editing and exporting

**Figures 1 to 3 (draw.io).** Open the `.drawio` file in draw.io (desktop or https://app.diagrams.net). Arrows are attached to their blocks, so moving a block keeps its connections. Export with *File > Export as > PDF* (tick *Crop*), then produce PNG at 300 dpi and SVG. From the command line:

```bash
drawio -x -f pdf --crop -b 8 -o diagram_2_datapath_clock_domain.pdf diagram_2_datapath_clock_domain.drawio
pdftoppm -r 300 -png -singlefile diagram_2_datapath_clock_domain.pdf diagram_2_datapath_clock_domain
pdftocairo -svg diagram_2_datapath_clock_domain.pdf diagram_2_datapath_clock_domain.svg
```

**Figure 4 (WaveDrom).** Paste the `.json5` contents into https://wavedrom.com/editor.html, or render with `npx wavedrom-cli@3.2.0 -i diagram_4_timing_output_release_gate.json5 -s out.svg`. Every `wave` string must stay 19 characters long, one per clock cycle.

SVG exports have their text converted to outlines, so they display the same in any application that accepts SVG.
