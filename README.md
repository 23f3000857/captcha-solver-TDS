# Captcha Solver (Client-side OCR)

## Overview
This is a browser-only captcha solver web app. It:
- Displays a captcha image from the URL parameter `?url=https://.../image.png` (or a built-in sample if not provided).
- Processes the image client-side with grayscale, contrast, adaptive (Otsu) thresholding, and basic morphology to enhance legibility.
- Uses OCRAD.js for OCR and tries multiple processing variants, selecting the best match.
- Shows the detected text, typically within 15 seconds.

No server or build step is required. Everything runs locally in your browser.

## Setup
- No installation needed.
- Files:
  - index.html (main app)
  - README.md (this file)

## Usage
1. Open `index.html` in a modern browser (Chrome, Edge, Firefox).
2. Optional: Provide a captcha image via query parameter:
   - Example: `index.html?url=https://example.com/captcha.png`
3. Alternatively, paste a URL into the input field and click “Load & Solve”.
4. If no URL is provided or the remote image blocks CORS, the app falls back to a generated sample captcha.
5. The app will attempt several preprocessing variants and display the best recognized text. A processing preview canvas is available to inspect the binarized image.

Notes:
- Remote images should permit cross-origin access (CORS) to be processed on a canvas in the browser. If not, download the image and open via a data URL or serve from a CORS-enabled location.
- Results quality depends on the complexity of the captcha; the app is tuned for simple alphanumeric captchas.

## License
MIT License

Copyright (c) 2025

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the “Software”), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED “AS IS”, WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.