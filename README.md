# Captcha Solver (Tesseract.js)

## Overview
This is a lightweight, client‑only web app that solves simple text-based captchas using Tesseract.js.

- Accepts a captcha image URL via the query parameter `?url=https://.../image.png`.
- Defaults to a built-in sample captcha if no URL is provided.
- Displays the target URL, the captcha image, and the recognized text.
- Includes basic preprocessing (grayscale + Otsu threshold + 2× upscaling) to improve accuracy.
- Attempts to handle cross-origin issues by automatically retrying through a CORS-enabled image proxy if needed.

Technologies:
- Pure HTML/CSS/JS (no build step)
- [Tesseract.js](https://github.com/naptha/tesseract.js) via CDN

License: MIT

## Setup
No build is required.

1. Download or clone the repository.
2. Open `index.html` in a modern browser with network access (models are loaded from CDN).

Notes:
- For best results and to avoid CORS issues, host `index.html` using a local static server (e.g., `npx serve`) or ensure the remote image allows cross-origin access.
- The app will try a CORS helper (`https://images.weserv.nl/?url=...`) automatically if direct loading is blocked.

## Usage
- Open the app:
  - Double-click `index.html`, or
  - Serve it locally and visit `http://localhost:PORT/index.html`.

- Solve a remote captcha:
  - Append `?url=FULL_IMAGE_URL`
  - Example: `index.html?url=https://example.com/captcha.png`
  - The app displays the URL being used and auto-starts solving.

- Upload from disk:
  - Click “Upload image” and pick a file; the solver runs automatically.

- Controls:
  - Load URL: uses the URL in the input field.
  - Solve / Solve again: re-runs OCR on the current image.
  - Show preprocessed: toggles between original and preprocessed image preview.
  - Copy text: copies the recognized text to the clipboard.

- Advanced:
  - You can tweak page segmentation mode via `?psm=line` or `?psm=auto` (default is `SINGLE_WORD`).

## License
MIT License

Copyright (c) 2025

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the “Software”), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED “AS IS”, WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.