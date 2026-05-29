> **DISCLAIMER:** This tool is NOT meant to ruin the fun of exploring — it's meant to save your sanity when you're stuck at 99% roads discovered and can't find that last tiny segment!

# FH6 Screenshot Road Finder

**[Try it live](https://thisisskay.github.io/fh-road-finder-web/)**

A free, browser-based tool that helps you find the last few undiscovered roads in Forza Horizon 6.

Drop in a map screenshot and the tool instantly highlights any pixels matching the undiscovered-road grey. Zoom in, pan around, change colours, and adjust tolerance — all live, no page reload needed.

**No installation. No server. No sign-up. Your images never leave your browser.**

## How It Works

1. Open the tool in any modern browser (Chrome, Edge, Firefox).
2. Drag and drop a Forza Horizon 6 map screenshot.
3. The tool scans every pixel for the undiscovered-road grey (RGB 128, 128, 128) and highlights matches instantly.
4. Adjust tolerance, highlight colour, line thickness, and output mode — the view updates in real time.
5. Zoom in and pan around to find small road segments.
6. Download the result as PNG.

## Features

- **Live scanning** — results update as you adjust settings, no button clicks needed.
- **Zoom and pan** — scroll to zoom into any area, drag to pan. Use the 1:1 button to see actual pixels.
- **Line thickness** — dilate detected pixels so even a single-pixel match becomes a visible dot.
- **Multiple highlight colours** — red, green, yellow, cyan, magenta, orange, white, or pick any custom colour.
- **Three output modes** — Overlay (highlights on original image), Black (highlights on black background, easiest to scan), and Transparent (for layering).
- **Works with JPEG and PNG** — JPEG compression shifts colours, so use tolerance 5 or higher. PNG gives the most accurate results.

## Privacy

All processing runs locally in the browser using JavaScript and the Canvas API. No images are uploaded, no data is sent anywhere, and the tool works fully offline after the page loads.

## Tolerance Guide

Tolerance controls how close a pixel must be to the target grey to count as a match. Each colour channel (R, G, B) is checked independently.

| Value | Name | Use case |
|-------|------|----------|
| 0 | Ultra strict | Exact match only. Clean PNG screenshots. |
| 1–2 | Strict / Normal | Small margin. Good for PNG. |
| 5 | Loose | Start here for JPEG screenshots. |
| 8+ | Very loose | Catches more but includes false positives. |

JPEG compression shifts pixel colours, so a pixel that was exactly (128, 128, 128) in-game may become (126, 129, 127) in a JPEG file. Higher tolerance compensates for this.

## Compatibility

This tool was built and tested for **Forza Horizon 6**. It may also work with other Forza Horizon titles if the map uses a similar grey for undiscovered roads, but it has not been tested on Forza Horizon 5 or earlier games. The target colour can be changed under Advanced settings if needed.

## Technical Notes

- Pure HTML, CSS, and JavaScript. No frameworks, no build step, no dependencies.
- Optimised for screens from 1080p to 4K, including ultrawide displays up to 32:9.
- Works locally by opening `index.html` directly, or hosted on any static web server including GitHub Pages.

## Credits

Built for the Forza Horizon 6 community. Open source, no tracking, no ads.
