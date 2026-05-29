# FH6 Screenshot Road Finder

A fully browser-based tool that detects possible undiscovered roads in Forza Horizon 6 map screenshots by scanning for pixels matching a target grey colour.

No installation needed. No server. No uploads. Everything runs locally in your browser.

## What the Tool Does

FH6 Screenshot Road Finder helps you find the last few missing roads in Forza Horizon 6. It scans your map screenshots for pixels matching the grey colour used for undiscovered roads, then highlights them so you can see exactly where to drive.

This tool was built and tested for Forza Horizon 6. It may also work with other Forza Horizon games if the map uses a similar grey colour for undiscovered roads, but it has not been tested on Forza Horizon 5 or earlier titles.

## How It Works

1. Open `index.html` in any modern browser (Chrome, Edge, Firefox).
2. Drag and drop a Forza Horizon 6 map screenshot, or click to choose a file.
3. The tool automatically scans the image and highlights matching pixels.
4. Adjust the tolerance slider, highlight colour, line thickness, and output mode in real time.
5. Zoom in and pan around to find small road segments.
6. Download the result as PNG.

The scan uses per-channel colour distance to detect matching pixels:

```
abs(R - 128) <= tolerance AND abs(G - 128) <= tolerance AND abs(B - 128) <= tolerance
```

## Privacy

All image processing happens locally in your browser. Your screenshots are never uploaded to any server. The tool works entirely offline after the page loads.

## Output Modes

- **Overlay** — original image with matched pixels blended in a highlight colour.
- **Black** — black background with matched pixels in the highlight colour. Best for spotting small clusters.
- **Transparent** — transparent background with matched pixels in the highlight colour. Useful for layering over other images.

## Tolerance Guide

Tolerance controls how close a pixel must be to the target colour (per channel) to count as a match.

| Value | Name | Best for |
|-------|------|----------|
| 0 | Ultra strict | Clean PNG screenshots only |
| 1 | Strict | Clean PNG screenshots |
| 2 | Normal | Good default for PNG |
| 5 | Loose | Recommended for JPEG screenshots |
| 8 | Very loose | Wide net, more false positives |

JPEG compression shifts pixel colours. A pixel that was exactly (128,128,128) in-game may become (126,129,127) in a saved JPEG. Higher tolerance compensates for this. For best results, save your screenshots as PNG.

## Use Locally

Open `index.html` in your browser. No server needed. It works directly from your local files.

## Deploy on GitHub Pages

1. Push these files to a GitHub repository:

```
index.html
style.css
app.js
README.md
```

2. Go to **Settings > Pages**.
3. Set the source to the branch and folder containing `index.html`.
4. Your tool will be live at `https://yourusername.github.io/your-repo/`.

`.nojekyll` is optional. It can be added if you want GitHub Pages to skip Jekyll processing, but it is not required for this simple static HTML/CSS/JS tool.

## Screenshot Tips

- Use **PNG** format for best accuracy (Win+Shift+S, paste into Paint, save as PNG).
- Zoom the in-game map so the area of interest fills the screen.
- Avoid UI overlays (menus, tooltips, popups) covering the map.
- If using JPEG, start with tolerance 5.

## Notes

- The default target colour is RGB(128, 128, 128), which matches the undiscovered road grey in Forza Horizon 6.
- The target colour can be changed under Advanced settings if needed for other games.
- The line thickness slider dilates detected pixels, making tiny clusters easier to spot when zoomed out.
- The tool is optimised for screens from 1080p to 2160p, including ultrawide displays up to 32:9.

## Credits

Built for the Forza Horizon 6 community. Open source, no dependencies, no tracking.
