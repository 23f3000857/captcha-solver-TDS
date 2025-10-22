# Captcha Solver (Client-side, Browser)

MIT-licensed, single-page web app that loads a captcha image from a URL (`?url=...`), preprocesses it in the browser, and solves it using Tesseract.js (WASM). No server required.

## Overview

- URL parameter: pass your captcha image at `?url=https://.../image.png`
- Default: if no URL is provided, the page generates a sample captcha locally
- Processing: grayscale + Otsu threshold + light morphology to denoise
- OCR: Tesseract.js (WASM) with character whitelist and single-line PSM
- Privacy: runs fully in your browser
- Performance: aims to display the solved text within ~15 seconds on typical connections/devices

## Setup

No build step required.

1. Download the two files in this repository.
2. Open `index.html` in a modern browser with internet access (for Tesseract.js assets).
   - Tesseract worker/core and language data are loaded from public CDNs.

License: MIT (see below).

## Usage

- Open `index.html`.
- To use a remote captcha:
  - Append the query string parameter `url`, for example:
    - `index.html?url=https://your.cdn.example/captcha.png`
  - The app will:
    - Fetch the image (with CORS fallbacks),
    - Display the original image,
    - Preprocess it on a canvas,
    - Run OCR and show the solved text.
- Interact via the UI:
  - Paste a URL and click “Load & Solve”.
  - Or choose a local image file.
  - Click “Re-run Solve” to retry with the current image.

Notes:
- If the remote server blocks CORS, the app attempts to fetch through safe, public CORS proxies.
- OCR accuracy depends on captcha complexity and obfuscation; classic simple captchas work best.

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