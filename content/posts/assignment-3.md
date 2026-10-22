+++
date = '2026-10-22T23:45:00+03:00'
draft = false
title = 'Assignment 3'
+++
## Goal

Design a box to hold the rocket, drawn as a flat net that folds into a closed rectangular box.

## Design

I sketched the net as a 2D sketch in Fusion 360. The box is a rectangular prism, 105 mm long with a 54 mm x 54 mm square cross-section.

![Flat net of the rocket box in Fusion 360](/Digital-Fabrication/assignment-3/box-sketch.png)

### Parts of the net

| Part | Shape | Dimensions | Purpose |
|---|---|---|---|
| Main faces (x4) | Rectangle | 105 mm x 54 mm | The four long sides that wrap around the rocket |
| Glue flap | Rectangle | 105 mm x 17 mm | Joins the last long face to the first to close the tube |
| End faces (x2) | Square | 54 mm x 54 mm | Close the two ends of the box |
| Dust flaps (x4) | Trapezoid | Bases 54 mm and 44 mm, height 25 mm | Fold in under the end faces to keep them square and stop gaps |
| Tuck flap necks (x2) | Trapezoid | Height 14 mm | Connect each end face to its tuck flap |
| Tuck flaps (x2) | Rectangle | 43 mm x 46 mm | Slide inside the box to hold each end shut |

The dust flaps and tuck flaps are narrower than the faces they attach to (44 mm and 46 mm instead of 54 mm). This leaves clearance so they slide in without catching on the inside walls once the box is folded.

Overall size of the flat net: 327 mm x 233 mm.

### Design process

1. Started from the main 105 mm x 54 mm face at the centre of the sketch and used a centre-point rectangle so the whole net stays symmetric about the origin.
2. Stacked the other three long faces and the 17 mm glue flap above and below it.
3. Added the two 54 mm x 54 mm end faces on the left and right, then the tapered necks and tuck flaps.
4. Added the four trapezoid dust flaps on the sides of the long faces.
5. Fully constrained the sketch with dimensions so a single value can be changed later if the rocket size changes.

## Fabrication

I cut the net out of cardboard on the laser cutter. The outline was set to cut all the way through, and the fold lines were set to score, so the laser only marked the surface. This let the cardboard fold cleanly along each line without separating.

## Result

The folded box made from brown cardboard, holding the 3D-printed rocket parts: body sections, fins, and nose cone.

![Finished cardboard box holding the rocket parts](/Digital-Fabrication/assignment-3/box-photo.jpg)
