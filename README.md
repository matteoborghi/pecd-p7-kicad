# PECD P7: SiC traction inverter board (KiCad)

KiCad project of the board behind the report
[pecd-p7-report](https://github.com/matteoborghi/pecd-p7-report): a
three-phase two-level SiC traction inverter, 800 V DC link, 30 A rms per
phase, 20 kHz. The board is 6 layers, 1.6 mm thick, revision 1.2.

The report covers only the power stage. On the PCB it is the area marked
with a dashed box and a name on layer `User.1`.

## Schematic

The root sheet `PECD_P7.kicad_sch` has six hierarchical sheets:

| Sheet | Content |
|---|---|
| `1_power_stage` | six SiC MOSFETs (E3M0016120K), DC-link capacitors, shunts, DC and phase terminals |
| `2_gate_drive` | isolated gate drivers |
| `3_phase_sense` | current and voltage measurement |
| `4_aux_supply` | auxiliary supplies |
| `5_control_if` | interface to the controller |
| `6_dclink_mgmt` | DC-link management |

`leg.kicad_sch` is the half-bridge used three times in the power stage.
`drv_channel.kicad_sch` and `sense_channel.kicad_sch` are the repeated
gate-drive and measurement channels.

## Libraries

Symbols, footprints and 3D shapes of the parts that are not in the KiCad
standard libraries are in `PECD_P7.kicad_sym`, `PECD_P7.pretty` and
`PECD_P7.3dshapes`. The notes on each library file (in Italian) are in
`librerie/NOTE_librerie.md`.

## Tags

- `pcb-v1.0`, `pcb-v1.1`, `pcb-v1.2`: board revisions.
- `exam-v1`: board with the power-stage box used by the report.

The default branch is `for-exam`, which adds the power-stage box to `main`.
