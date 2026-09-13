# Hosting this folder

Already built. Serve over **HTTPS** - the webcam will not work over plain HTTP.
Relative asset paths, so the same folder works at a domain root or a sub-folder.

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

## Doing a calibration test run

1. Open the site, allow the camera.
2. Work through the corner step, the nine-point calibration and the check.
3. On the results screen press **Download calibration diagnostics**.

You can stop there - the video is not needed. The file is about 3.6 MB of
coordinates and numbers: model inputs, fitted weights, environment, and the raw
face landmarks behind them. No images or video.

## At the end of a full run

**Explore results** opens the linked video + timeline view. Downloads: CSV,
detailed CSV (101 columns), JSON, and the diagnostics file.

## Changing the video

Replace `videos/test-video.mp4` with your own MP4 using the same filename.
