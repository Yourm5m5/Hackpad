# Hackpad Journal

A 3-key media macropad built on the Seeed XIAO RP2040, running KMK firmware.

**Total time: 4 hours**

---

## Day 1 – 11 Oct 2026: Planning, schematic & PCB
**Time spent:** 1.5 hours

### What I did
- Decided to build a small media macropad: 3 keys, controlling volume and music
- Picked the **Seeed XIAO RP2040** because it's tiny, cheap, has USB-C and
  works with CircuitPython + KMK
- Drew the schematic in KiCad: XIAO RP2040, 3 MX switches, diodes
- Laid out the PCB around the XIAO footprint with the 3 switches in a row
- Added mounting holes for M3 screws so the PCB screws into the case
- Ran DRC and fixed the errors

### Problems
- [e.g. the first switch footprint was the wrong spacing, swapped to the MX 1U footprint]
- [e.g. traces were too close to a mounting hole, rerouted]

![Schematic](images/schematic.png)
![PCB layout](images/pcb.png)

---

## Day 2 – 12 Oct 2026: Case design
**Time spent:** 1.5 hours

### What I did
- Modelled the case in [Fusion 360 / Onshape] around the PCB outline
- Two-part case: a **top plate** that holds the switches and a **bottom shell**
  that holds the PCB
- Added bosses for **M3 × 5 mm brass heat-set inserts** so the case can be
  opened and closed many times without stripping the plastic
- Added a cut-out for the XIAO's USB-C port
- Exported renders of the case and full macropad

### Decisions
| Decision | Why |
|---|---|
| Heat-set inserts instead of screwing into plastic | Stronger and reusable |
| 3 keys only | Covers volume + media without taking much desk space |
| DSA keycaps | Uniform profile, look clean on a small pad |

![Case model](images/case.png)
![Render](images/render.png)

---

## Day 3 – 13 Oct 2026: Firmware, BOM & README
**Time spent:** 1 hour

### What I did
- Set up the firmware: **CircuitPython + KMK**
- Used KMK's **TapDance** module so each key has 2 functions (6 total):
  - Key 1: tap = mute, double-tap = play/pause
  - Key 2: tap = volume up, double-tap = next track
  - Key 3: tap = volume down, double-tap = previous track
- Set the double-tap window to 250 ms so it feels responsive without misfires
- Put together the BOM with AUD prices from AliExpress (≈ $46 total)
- Wrote the README with setup instructions, keymap and gallery

### What I learned
- How KMK's TapDance works and how to tune tap timing
- How to design a case around heat-set inserts

### Next steps
- [ ] Order the PCB and parts
- [ ] Print the case
- [ ] Assemble, flash and test
      
