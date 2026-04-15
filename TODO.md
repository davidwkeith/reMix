# re:Mix 120V (US) Conversion — Research TODO

This document tracks the research and sourcing needed to build a 120V/60Hz version
of the re:Mix for North American use (NEMA 5-15P, 120VAC).

## Motor (BOM #33)

- [ ] Contact Junhui Electric about a 120V version of Art. Nr. 7635
  - Must match shaft diameter (8mm), body dimensions, and mounting pattern
  - Must fit within Motor Adaptor (#15) and Ventilation Pipe (#25) cavity
- [ ] If unavailable, measure the 230V motor precisely and source a dimensional equivalent
  - Body diameter (constrained by ~96mm inner diameter of bottom/top panels)
  - Mounting bolt pattern
  - Shaft length and diameter
  - Target wattage: 300-500W range (match original)
- [ ] Confirm motor gear (#11, PA66+GF30) torque rating is compatible with the 120V motor's output

## Power Cable (BOM #39)

- [ ] Source a NEMA 5-15P appliance cord
  - 16 AWG / SPT-2
  - ~1400mm length
  - Stripped/tinned ends on the appliance side
- [ ] Verify cord fits through the Cable Fixer (#27) and enclosure routing

## Electrical Components — Verify Ratings at 120V / Higher Current

At 120V the motor draws roughly double the current (~4A vs ~2A) for the same wattage.
All inline components must be rated for this higher current.

- [ ] **Rotary switch (#34)** — Towei B3200-411GR: look up datasheet, confirm current rating
      handles ~4-5A at 120VAC
- [ ] **Micro switch (#37)** — OMRON SS-10GL-3: rated 10A/125VAC — confirmed OK
- [ ] **Choke (38 µH)** — verify current rating handles ~4-5A (was sized for ~2A at 230V)
- [ ] **C1 (0.22 µF)** — verify voltage rating is at least 250VAC (likely fine)
- [ ] **C2, C3 (JY332M, X1 400VAC / Y2 300VAC)** — confirmed OK for 120V
- [ ] **Thermal fuse (17AM1033A5)** — temperature-based, not voltage-dependent — confirmed OK
- [ ] **R1 (1 MOhm)** — bleeder resistor, voltage-independent — confirmed OK
- [ ] **Ferrules (#35)** — VT AEHI 0,75-100: confirm crimp size matches 16 AWG wire
      (0.75mm² ≈ 18 AWG; 16 AWG = 1.3mm² — may need larger ferrules)

## Sourcing Strategy — Thrift Store Donor Blender

The easiest way to get a 120V motor (and other parts) for a single build is to
harvest from a cheap secondhand blender. A $5-10 thrift store find gets you a
known-working motor, cord, and suppression components.

### Parts to salvage from a donor blender

- [ ] **Motor** — the main prize, must be 76-series frame (76mm diameter), 400-600W
- [ ] **Power cord** — any 16-18 AWG 120V cord works
- [ ] **Thermal fuse / protector** — usually inline with motor, already rated for 120V current
- [ ] **EMI suppression capacitors** — X and Y safety caps across motor terminals
- [ ] **Motor brushes** — if same frame size, keep as spares (brushes are the wear item)

### Brands to seek

- **Oster** — uses 76-series frame motors, extremely common at thrift stores
- **Hamilton Beach** — 400-500W models are ubiquitous and cheap secondhand
- **KitchenAid** (small blenders) — decent motor quality
- **Waring** — commercial-adjacent quality, good motors

### Brands to avoid

- **Nutribullet / Magic Bullet** — smaller non-standard motor frames, won't fit 76mm cavity
- **Ninja** — oddly-shaped motors with integrated plastic housings, hard to extract
- **Any "personal blender" / single-serve** — too small, typically 200-300W
- **Anything brushless/DC** — newer Vitamix, some Breville use brushless DC motors
  with external controllers, won't work with the re:Mix rotary switch circuit

### What to check at the store

- [ ] Wattage on the label — look for 400-600W
- [ ] Spin the blade coupling by hand — should turn freely with slight brush drag (seized = skip)
- [ ] Physical size — standard upright base (not personal/single-serve) = likely 76-series motor
- [ ] Look for a round motor canister, not a molded-in plastic housing

### After purchase — before disassembly

- [ ] Measure donor motor: body diameter, shaft diameter (need 8mm), shaft length
- [ ] Check if Motor Adaptor (#15) needs reprinting to fit (it's 3D-printed ASA, easy to modify)
- [ ] Check if Ventilation Pipe (#25) needs reprinting to fit

## No Changes Required

These parts are voltage-independent and carry over as-is:

- All mechanical components (blades, gears, bearings, seals, panels, enclosure)
- All 3D-printed parts
- All CNC-milled parts
- Solder (#38)
- Heat shrink tube (#36) — rated 600V
