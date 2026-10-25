# ASCII 3D

Turn photos into a 3D model drawn in ASCII, then drag to rotate it and see it from any side.

Everything runs in the browser. Photos are never uploaded anywhere.

## Modes

- **3 or more photos around an object (reconstruction).** Each photo is cut out from its background and a 3D shape is carved from the silhouettes (visual hull). Photos must be evenly spaced around the object, first photo = front, going around in one direction, same distance and height, plain background. Hollows and concave parts cannot be recovered from silhouettes. Tested so far only on synthetic renders, not on real turntable photos.
- **1 or 2 photos (estimate).** The outline is inflated into a rounded body, optionally using a free in-browser depth model (Depth Anything V2 small, ~25 MB, loaded from a CDN on first use), then mirrored for the back. The hidden back and sides are a guess, not a measurement.

## Use

Open `public/index.html` in a browser or deploy the `public` folder to any static host. No build step, no dependencies, no keys.

## Known limits

- Cutout works best on a plain or smoothly shaded background. Low-contrast subjects (white object on grey) may need the Cutout slider.
- Thin parts (handles, spouts) can be lost at low Detail.
- Not tested on real multi-photo captures.
