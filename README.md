# CS180 — Project 0 (Becoming Friends with Your Camera)

This repository contains a complete, aesthetic single-page site for Project 0.

## Structure

```
cs180-proj0/
├─ index.html
└─ media/
   ├─ part1/              # 3 images (selfie close, backed-up+zoom, variation)
   ├─ part2/              # 2 images (far+zoom vs close+wide)
   └─ part3/
      ├─ frames/          # optional frames to build GIF/MP4
      ├─ dollyzoom.mp4    # or dollyzoom.gif
      └─ dolly-poster.jpg # poster frame for the video
```

> Replace the placeholders in `media/**` with your visuals. Keep the filenames or update `src` paths in `index.html`.

## Create the GIF/MP4

- **ImageMagick (GIF)**

```bash
magick convert -delay 8 -loop 0 media/part3/frames/*.jpg -resize 1280x720 -layers Optimize media/part3/dollyzoom.gif
```

- **FFmpeg (MP4)**

```bash
ffmpeg -framerate 12 -pattern_type glob -i 'media/part3/frames/*.jpg' \
  -vf scale=1280:-2 -c:v libx264 -pix_fmt yuv420p -crf 20 media/part3/dollyzoom.mp4
```

## Publish on GitHub Pages

1. Create a new repo (e.g., `cs180-proj0`), then upload this folder.
2. Commit and push to `main`.
3. In **Settings → Pages**, choose **Deploy from branch**, select `main` and `/ (root)`.
4. Wait for the site to build; your page will be available at the Pages URL.

## Export PDF for Gradescope

Open the site in your browser, press **Print**, and enable **Headers & Footers** so the **URL** appears on the PDF. The page includes print-friendly styles.

— Generated 2025-09-03
