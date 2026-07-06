# Image Compressor

Compress and resize images in your browser. Fully local, no upload, no account.

**Live demo:** https://0xelitesystem.github.io/image-compressor/

## Use

1. Open the tool and drop one or more images onto the drop zone, or click to browse. JPEG, PNG, WebP, GIF, and BMP are accepted.
2. Pick an output format:
   - **JPEG** is smallest for photos.
   - **WebP** is a modern format that usually beats JPEG at the same quality (offered only when your browser can encode it).
   - **PNG** is lossless, best for graphics and screenshots with sharp edges.
   - **Keep original format** re-encodes each image in its own format.
3. Drag the **Quality** slider to trade size for fidelity. It applies to JPEG and WebP. PNG is lossless, so quality is ignored there.
4. Choose a **Resize** option:
   - **Keep original dimensions** recompresses only.
   - **Fit within a maximum size** scales the longest side down to your pixel limit and never upscales.
   - **Scale by percentage** shrinks by a percent of the original.
5. Every image shows its before and after dimensions, file size, and the percentage saved. Download them one at a time, or grab everything at once as a `.zip`.

All processing happens the moment you drop a file. Re-encoding through the canvas also strips embedded metadata such as GPS coordinates and camera details, which is a useful side effect before sharing photos.

## Why this exists

Most "image compressor" sites upload your photos to a server you do not control, wrap the result in ads and trackers, and cap you at a few files per day. There is no reason for any of that. A browser already ships with a full image decoder and a canvas encoder, so the entire job can run on your own machine with zero network calls.

This tool is one static HTML file. No surveillance, no build step, no dependencies, MIT licensed. Read it, host it yourself, or keep a copy offline. What you see is the whole thing.

## Privacy

Everything runs in your browser. Your images are decoded, resized, and re-encoded locally using the canvas API, and the resulting files are handed straight back to you. Nothing is uploaded, nothing is logged, and nothing leaves your machine. There are no analytics, no cookies, and no network requests of any kind. You can confirm this by opening your browser network tab, or by loading the page once and then using it with your connection turned off.

## Run locally

Clone the repository and open the file directly:

```
git clone https://github.com/0xelitesystem/image-compressor.git
cd image-compressor
```

Then open `index.html` in any modern browser. Because it is a single file with no dependencies, double-clicking it works.

If your browser restricts something when opening from `file://`, serve the folder over HTTP instead:

```
python -m http.server
```

Then visit http://localhost:8000.

## Build

There is no build. The tool is one self-contained `index.html` with inline CSS and JavaScript and no external resources. Edit the file, reload the page, done.

## License

MIT. See [LICENSE](LICENSE).

## Related

- https://github.com/0xelitesystem/jwt-inspector
- https://github.com/0xelitesystem/eeat-signals-reference
