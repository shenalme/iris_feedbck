# Hosting this folder

Already built. Serve over **HTTPS** - the webcam will not work over plain HTTP.

## Checking which version is deployed

The welcome and completion screens show a **Build** timestamp. If it does not
change after uploading, the new files are not live yet.

## Updating a GitHub Pages site

Upload `index.html` **and** the whole `assets` folder together. Commit, wait for
the tick, hard-refresh (Ctrl-Shift-R / Cmd-Shift-R).

## First-time setup

GitHub does not unzip archives. Extract this zip, then upload what is inside it.

1. Create a **public** repository.
2. **Add file -> Upload files**, drag in `index.html` and the `assets`,
   `mediapipe` and `videos` folders. Commit.
3. **Settings -> Pages -> Source: Deploy from a branch**, branch `main`,
   folder `/ (root)`. Save.

## New in this build

**Explore results** now offers five visualisations, switched with chips above
the controls:

- **Live dot** - current estimate with a short trail
- **Trail** - the path taken, fading with age
- **Scatter** - every raw estimate as a point, for judging noise
- **Scanpath** - numbered fixation circles joined by saccade lines
- **Heatmap** - accumulated attention density

A **time range** control switches between a rolling window, everything up to
the playhead, and the whole video. Sliders adapt to the chosen mode: size,
opacity and trail length for point modes; spread, intensity and contrast for
the heatmap. Scanpath adds toggles for numbering and saccade lines.

All of it works alongside the existing Raw / Cleaned / Both control.

## Downloads at the end of a run

CSV, detailed CSV, JSON, and the calibration diagnostics file.
