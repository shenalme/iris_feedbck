# Hosting this folder

Already built. Serve over **HTTPS** - the webcam will not work over plain HTTP.

## Checking which version is deployed

The welcome and completion screens show a **Build** timestamp. If it does not
change after uploading, the new files are not live yet.

## Updating a GitHub Pages site

Upload `index.html` **and** the whole `assets` folder together. Commit, wait for
the tick, hard-refresh (Ctrl-Shift-R / Cmd-Shift-R). `mediapipe` and `videos`
only need re-uploading if they changed.

## First-time setup

GitHub does not unzip archives. Extract this zip, then upload what is inside it.

1. Create a **public** repository.
2. **Add file -> Upload files**, drag in `index.html` and the `assets`,
   `mediapipe` and `videos` folders. Commit.
3. **Settings -> Pages -> Source: Deploy from a branch**, branch `main`,
   folder `/ (root)`. Save.

## What changed in this build

Calibration now visits its nine targets in random order, cross-validation holds
out whole targets rather than individual samples, the drift-prone head-position
features have been removed, and head orientation is regularised separately. On
the diagnostics session these halved validation error, 129 px to 65 px.

The check screen now also warns if viewing distance changed during calibration.

## Sitting position matters more than anything else

Settle into a comfortable position *before* starting calibration, and try not to
drift closer or further away during it. Distance changing by 15% mid-calibration
costs more accuracy than any model change can recover.

## Downloads at the end of a run

CSV, detailed CSV (101 columns), JSON, and the calibration diagnostics file.
**Explore results** opens the linked video + timeline view.
