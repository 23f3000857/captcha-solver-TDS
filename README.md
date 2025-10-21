# Captcha Solver (Client-side OCR)

MIT-licensed, single-page web app that solves simple captchas from a URL query parameter using in-browser OCR (Tesseract.js). Includes lightweight image preprocessing to improve recognition accuracy and aims to display the solved text within 15 seconds.

## Overview

- Input source: Captcha image specified via the url query parameter (?url=...).
- Default sample: A built-in SVG captcha is used if no URL is provided.
- OCR engine: Tesseract.js running entirely in the browser; no server required.
- Preprocessing: Grayscale and Otsu thresholding to produce a clean, binarized image for OCR.
- UX: Displays the captcha image, preprocessed preview, progress logs, recognized text, confidence, and elapsed time.

Caveat: OCR quality depends on the captcha’s complexity. Highly distorted or noisy captchas may not be solvable reliably.

## Setup

No build steps required.

1. Download or clone the repository contents.
2. Ensure the following files exist at project root:
   - index.html
   - README.md

License: MIT (see bottom of this README).

## Usage

- Open index.html directly in a modern browser, or serve it via any static file server.
- To solve a specific captcha image, pass its URL via the url query parameter:
  - Example: file:///path/to/index.html?url=https://example.com/captcha.png
  - The page shows the exact URL being used, the image preview, and the recognized text.

Tips:

- For best results, ensure the captcha image server permits CORS (Cross-Origin Resource Sharing). If the remote server blocks CORS, OCR may not access the pixels. Workarounds:
  - Download the captcha image locally and open via a file:// or same-origin URL.
  - Use a CORS-enabled endpoint or host the image with appropriate Access-Control-Allow-Origin headers.
- The app auto-loads and auto-solves on page open if url is present.
- Click Reset to revert to the built-in sample and solve again.

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