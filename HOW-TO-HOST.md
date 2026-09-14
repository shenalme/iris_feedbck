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

**Explore results** now shows raw and cleaned gaze, switched with a
**Raw / Cleaned / Both** control.

Cleaning applies the drift correction fitted from the validation points, then
removes blinks, off-screen estimates, single-frame mistracks and stretches where
the head left the calibrated range, then fills gaps short enough to bridge.
A Data quality ribbon on the timeline shows kept, filled and removed across the
session, and the Cleaning panel counts what went and why.

The recording is never modified. Switch to Raw to see exactly what was removed.

The detailed CSV gained `cleanX`, `cleanY`, `cleanVideoX`, `cleanVideoY`,
`cleanKept` and `cleanReason`, so the same decisions are reproducible outside
the browser.

## Downloads at the end of a run

CSV, detailed CSV, JSON, and the calibration diagnostics file.
