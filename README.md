# horita-sct-50-notes

The SCT-50 is a Horita serial-controlled character generator that overlays text on a composite video signal.

My unit seems to have older firmware than the Rev D manual expects, but it is still serviceable. 

Note that these CGs have a soldered 4.4V NiCd battery that will need to be replaced.

## Setup

Toggling the front switch to `Setup` allows some basic configuration. This is what I’m currently using:

| Setting | Value | Setting | Value |
|---|---|---|---|
| CHAR | WHITE | BACK | ON |
| CONT | LOW | FLSH | OFF |
| HPOS | 17 | VPOS | 24 |
| HSIZ | 1X | VSIZ | 2X |
| MODE | NOR | ADRS | 00 |
| TIME | OFF | Time line/position | L?, 00:16: |
| DATE | OFF | Date line/position | L5, 02-17-09 |
| ID | ON | SAVE ID? | NO |
| SAVE THIS SETUP? | YES | | |

To save, navigate with the toggles to `SAVE THIS SETUP?` so it displays `YES` and then flip the `SETUP` toggle back.

## Set ID

The ID displayed when the unit powers up can be set over serial. Connect the unit via a straight-through DE-9 cable to a computer and connect to it via 9600bps, 8-N-1.

Below is the series of commands to have the ID set to “Intermod Cablevision”:

1. `Esc` `00` `20`
2. `Esc` `00` `22`
3. `Esc` `00` `25` (clear)
4. `Esc` `00` `26` `067`
5. `Esc` `00` `27` then type `INTERMOD`
6. `Esc` `00` `26` `105`
7. `Esc` `00` `27` then type `CABLEVISION`

Note that `Esc` requires pressing the `Esc` key on the keyboard.

To save ID, go back into `Setup` via the toggle switch and set the `SAVE ID` option to `YES` before navigating to `SAVE THIS SETUP?` and toggling so it displays `YES` and then flip the `SETUP` toggle back.
