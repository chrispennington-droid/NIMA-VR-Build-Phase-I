# NIMA Phase II — Drawing File Index for Claude Code
*Place all files in this index in the same folder as `nima_phase2_ar.py` before running.*

---

## FILE LIST & PURPOSE

| Filename | Type | What It Shows | What to Read From It |
|---|---|---|---|
| `Outlines_for_NIMA_Build_Degrees.jpg` | JPG | Overall site plan with angle annotation | High-Bay rotation = 100° from E-W line = **-10° Z in Blender** |
| `Outlines_for_NIMA_Build_Connector_with_measurment.pdf` | PDF | Connector footprint with ALL dimensions annotated | Primary source for all connector exterior dimensions |
| `Outlines_for_NIMA_Build_First_Floor_with_Rooms.pdf` | PDF | Overall first floor — both Connector and High-Bay together | Spatial relationship between the two buildings, junction alignment |
| `Outlines_for_NIMA_Build_First_Floor_with_Rooms_Connector.pdf` | PDF | Connector first floor room layout with dimensions | Interior wall positions F1, room bay grid, lab room sizes |
| `Outlines_for_NIMA_Build_First_Floor_with_Rooms_Highbay.pdf` | PDF | High-Bay first floor with dimensions | HB exterior dims (176' × 88'), door location, loading zone, bay widths |
| `Outlines_for_NIMA_Build_Second_Floor_with_Rooms.pdf` | PDF | Overall second floor — both buildings together | Overall second floor spatial layout, cyan slab extents |
| `Outlines_for_NIMA_Build_Second_Floor_with_Rooms_Connector.pdf` | PDF | Connector second floor room layout with dimensions | Interior wall positions F2, folding wall, lab bay grid |
| `Outlines_for_NIMA_Build_Second_Floor_with_Rooms_Highbay.pdf` | PDF | High-Bay second floor with dimensions | Cyan slab (28' × 60'), blue loading cover (60' × 24'), stair cutouts |

---

## GRID SCALE BY DRAWING

| Drawing | Grid square = |
|---|---|
| Overall drawings (First/Second Floor with Rooms — both buildings) | **8 ft × 8 ft per square** |
| Connector detail drawings | **4 ft × 4 ft per square** |
| High-Bay detail drawings | **4 ft × 4 ft per square** |
| Degrees drawing | Not to grid — annotation only |

---

## KEY DIMENSIONS ALREADY EXTRACTED (Pre-read — do not re-derive)

### From `Outlines_for_NIMA_Build_Connector_with_measurment.pdf`
- Connector north body: **85 ft EW × 70 ft NS**
- Connector south bump: **37 ft EW × 22 ft NS**, offset 48 ft from west edge
- Stair cutout 1 (cyan, "Second Story Only ceiling/slab/Cover"): **13.5 ft × 22 ft**
  - Position: NE corner of connector, X 71.5→85, Y 48→70
- Stair cutout 2 ("Cutout for Stairs in ceiling/slab"): **13.5 ft × 22 ft**
  - Position: X 71.5→85, Y 26→48
- HB stair cutout depth: **11.705 ft** (annotated dimension)
- Other annotated dimensions for reference: 66', 8', 11.705', 37', 35.5', 8', 6',
  28', 22', 68', 13', 5', 8.75', 3', 22'

### From `Outlines_for_NIMA_Build_First_Floor_with_Rooms_Highbay.pdf`
- High-Bay overall: **176 ft long axis × 88 ft short axis** (CONFIRMED annotations)
- First floor door (east wall): **3 ft wide, 2 ft from north end**
- Bay structural grid: **16 ft wide bays** (no interior walls — open production floor)
- Loading zone dimensions annotated: 76', 9', 52', 2', 8'
- Loading area south extent: part of 60' × 24' cover slab zone

### From `Outlines_for_NIMA_Build_Second_Floor_with_Rooms_Highbay.pdf`
- Cyan slab (connector junction, north end of HB): **60 ft wide × 28 ft deep**
  - HB local: X 14→74, Y 148→176, Z = 14.0 ft (STORY_1_H)
  - Two stair cutouts: each **8 ft wide × 11.705 ft deep**, symmetrical about X=44
- Blue loading cover slab (south end of HB): **60 ft wide × 24 ft deep**
  - HB local: X 14→74, Y -24→0, Z = 14.0 ft
  - **Roof cover only — no enclosing walls. Open below for tall equipment.**
- HB south wall: split at loading opening — only X 0→14 and X 74→88 are solid

### From `Outlines_for_NIMA_Build_First_Floor_with_Rooms_Connector.pdf`
- Primary NS walls at: X = 22, 44, 66 ft from connector west edge
- Primary EW walls at: Y = 24, 37, 48 ft from connector south edge
- Room bay modules: 22' EW bays, 16.875' | 11.125' sub-bays on west
- Individual lab rooms: 12'×12.833', 12'×9.666', 12'×15'
- Lobby/stair zone: X 66→85, open (no cross walls)

### From `Outlines_for_NIMA_Build_Second_Floor_with_Rooms_Connector.pdf`
- Primary NS walls at: X = 22, 44, 66 ft
- Primary EW walls at: Y = 12.5, 28, 41.5 ft
- Folding wall / moveable partition: X ≈ 65.33 ft (21.331' dim from annotation),
  spanning Y 28→41.5
- Lab bay grid: 20.75' wide × 11.75' deep, repeating
- NE zone: 11.875' × 11.875' sub-grid

### From `Outlines_for_NIMA_Build_Degrees.jpg`
- Angle annotation confirms: **100° from true east-west line**
- 90° from E-W = true north; 100° = 10° clockwise past north
- In Blender (North = +Y): **rotation_euler[2] = math.radians(-10)**

---

## BUILDING JUNCTION RULES (CRITICAL)

1. **Tyler → Connector**: Connector west wall (X=0) is a solid panel. The excluded
   existing Tyler Research Center is to the west. No gap, no opening at X=0.

2. **Connector → High-Bay**: Connector east wall (X=85, Y -22→70) is flush against
   HB west wall (HB local X=0, world X=85 at anchor). They share the same plane.
   The HB west wall south end (HB local Y=0) aligns with connector at world Y=0.
   **No gap, no opening, no separation between these buildings.**

3. **All three buildings connect seamlessly** — the AR experience has no visible
   gaps or voids at any building junction.

---

## HEIGHT REFERENCE (Derived from exterior elevation drawing)

| Measurement | Value | Source |
|---|---|---|
| High-Bay roof top elevation | 37.7888 ft | Elevation drawing |
| Connector roof top elevation | 29.2288 ft | Elevation drawing |
| Roof structural assembly depth | ~2.5 ft | Estimated (steel joist + deck) |
| High-Bay interior clear height | 35.2888 ft | 37.7888 − 2.5 |
| First floor floor-to-floor (structural) | 14.0 ft | Confirmed by reverse calc |
| First floor hung ceiling height | 9.6 ft | Matches existing Tyler Research Ctr |
| First floor ductwork plenum | 4.4 ft | 14.0 − 9.6 |
| Second floor ceiling — low | 8.0 ft | Sloped ceiling, low end |
| Second floor ceiling — high | 12.73 ft | 29.2288 − 14.0 − 2.5 |

**Validation**: 14.0 (F1) + 12.73 (F2 ceil high) + 2.5 (roof) = 29.23 ≈ 29.2288 ✓

---

## COORDINATE SYSTEM REMINDER

```
World origin (0,0,0) = SW corner of Connector at ground level
Blender: X = East, Y = North, Z = Up
North = +Y  ← never redefine this

Connector: axis-aligned, no rotation
High-Bay:  rotated -10° about Z, pivot at world (85*M, 0*M, 0)
```

---
*This index is a companion to `NIMA_Blender_AR_Prompt.md` and `nima_phase2_ar.py`*
*PSU Tyler Prove-out Facility — NIMA Phase II — schematic design 2024-05-03*
