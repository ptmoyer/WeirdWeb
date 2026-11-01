WALK POSE STUDY — IMPORT UPDATE

Open walk_pose_study.html in a modern browser; it works offline.

IMPORT JSON: Load the previous coordinate JSON format or a project JSON. Invalid files are rejected without replacing the study. Coordinate-only files retain the current image if its dimensions fit; verify that the artwork matches.

IMPORT SPRITE SHEET: Choose PNG, JPEG or WebP, set columns and rows, then Apply. Sheets must use a uniform grid without padding or gutters. Each row becomes an animation. Keep-and-scale preserves existing coordinates for matching rows and frames; added frames use a template pose and require manual tracing. Uncheck this option to start every frame with a template.

EDIT: Pause, drag joints on either right panel, step through frames or change row and speed.

EXPORT: Coordinate JSON saves joints only. Project JSON saves joints, embedded artwork and playback speed. Export before closing; edits are not saved automatically.

The GIF and alignment PNG show the original reference study. Coordinates are manual estimates, with hidden joints inferred. This is a 2D pose reference, not a 3D rig.

Validation: JavaScript syntax and automated logic tests passed for legacy/project imports, invalid files, grid sizes, coordinate scaling and frame wrapping. Full browser interaction testing was unavailable in this environment.

ONION SKINNING: Enable in the skeleton onion-skinning panel. Previous frames are pink, next frames green, and shared frames purple. Select 1–3 frames in each direction and adjust opacity. Distant frames fade further; ghosts wrap across the loop boundary and appear behind the current skeleton in both editable panels. Only the current pose responds to dragging. Project JSON preserves these settings. Coordinate-only imports reset them. Logic tests passed for loop wrapping, single-frame animations, deduplication and settings restoration.

CUTOUT RIGGING UPDATE
The editor now starts with your uploaded, edited joint coordinates.
Click Load demo mannequin to build simple articulated test artwork. Choose Play to preview it; choose Pause to edit. The demo is deliberately simple and is not finished knight artwork.
Upload transparent PNG/WebP parts, choose two joints, and drag A/B on the part image to attach it. Choose the animation row for front/back variants.
The part keeps its reference length unless Stretch is checked. Size adjusts the artwork around the first attachment point. Mirror flips the artwork before attachment.
Per-frame offsets, rotation, scale, layer offset and hide controls are stored separately for each part and animation frame. For alternate angles, add another part and toggle Hide per frame.
Export all rows as PNG sheet exports only the character on transparency. Export project JSON preserves all cutout images, joints, pivots, layers and adjustments. Coordinate-only JSON does not include cutout artwork. Loading coordinate-only JSON or applying a new sprite-sheet grid clears the cutout rig; export your project first.
The demo sheet PNG is an example export, not an animation-quality claim.
Verification: actual Canvas renderer tested and output inspected; demo creation, PNG export, project roundtrip, attachment math, frame overrides and invalid-rig rejection passed. Existing JSON import and onion-skin tests also passed. Browser-specific drag interactions have not been verified in a live browser.
