The trial data is currently embedded directly in the HTML as const D = {...}. 
To use different data files, replace this object with new data matching the same schema.

## Fiber Layout

The insole grid is 60 rows x 21 columns. Fibers are at fixed positions:

```
        col 7   col 10  col 13
         V1      V2      V3
          |       |       |
row 11 ───┼───────┼───────┼───  H1 (toe)
row 16 ───┼───────┼───────┼───  H2
row 22 ───┼───────┼───────┼───  H3 (midfoot)
row 38 ───┼───────┼───────┼───  H4
row 51 ───┼───────┼───────┼───  H5 (heel)
          |       |       |
```

- 5 horizontal fibers (H1–H5): HR = [11, 16, 22, 38, 51]
- 3 vertical fibers (V1–V3): VC = [7, 10, 13]
- 15 intersection points (5H × 3V)

## Key Formulas

Attenuation: normalized 0–1, where 0 = no pressure, 1 = max pressure:
```
atten = (baseline - signal) / (baseline - min)
```

Intersection pressure: geometric mean of crossing fibers:
```
intersection = √(hAttenuation × vAttenuation)
```
Both fibers were attenuated for the intersection.
