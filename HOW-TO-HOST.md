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

- Calibration is now a 5x5 grid (25 targets) instead of 3x3, with less time
  spent on each. Roughly 50 seconds end to end.
- The check stage looks different from calibration: a teal crosshair ring
  rather than the gold dot.
- The camera crops around the face when it is small in frame, so the tracker
  spends its input budget on the eyes rather than the room.
- Phones and tablets must be held in landscape. Portrait puts the camera at one
  end of a long screen, which is the worst geometry for horizontal gaze.
- Both CSVs now carry `deviceType`, so sessions from different hardware can be
  pooled and filtered later.

## Running on phones and tablets

Works, but prop the device against something solid. A handheld device moves
constantly relative to the eyes, which is what degrades the estimate most.
A laptop still gives the best data.

## Sitting position matters more than anything else

Settle into a comfortable position *before* calibrating and do not drift closer
or further during it. The check screen warns you if you did.

## Downloads at the end of a run

CSV, detailed CSV, JSON, and the calibration diagnostics file.
**Explore results** opens the linked video + timeline view.
