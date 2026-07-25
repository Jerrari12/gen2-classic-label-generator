# GEN2 Classic Pro Label Generator · Jerrari3D

A browser-based tool for creating custom **Classic Pro** faceplate labels for the GEN2 Modular Storage System. No install, no account - open `index.html` and go.

---

## What it does

Generates print-ready, two-color labels that snap into GEN2 Classic Pro faceplates. Each label has:

- **Auto-fitting text** that **word-wraps** to new lines and shrinks to fit the label's rectangular face.
- An **optional icon or letter/number** badge.
- Smart layout:
  - **Text only** → centered horizontally **and** vertically on the label.
  - **Icon + text** → the icon sits to the **left** of the text, every text line is left-justified to the icon, the icon is vertically centered to the text block, and the whole icon+text group is centered on the label.
  - **Icon only** → the icon is centered on the label.
- **Icons**: pick from the built-in set, or **upload your own SVG**.

The model is the Classic Pro label insert (47 × 25.5 × 1.5 mm) with the flexible compliant tabs at the bottom.

---

## How to use it

1. Type your text in each label row. Long text wraps automatically.
2. *(Optional)* Click the **badge button** (the `+` left of the text field) to add a letter/number, choose a built-in icon, or upload an SVG.
3. Adjust **Text height**, **Text depth**, and **Icon size** under Settings.
4. *(Optional)* Import a **CSV / TXT** file to create many labels at once (one label's text per row).
5. Click **Download .3mf**.

---

## Printing in two colors

The exported `.3mf` assigns the **base** to filament 1 and the **text + icon** to filament 2. Open it in OrcaSlicer, Bambu Studio, or PrusaSlicer; if your slicer doesn't auto-detect, set the base to a light filament and the text/icon to a dark one. 0.2 mm layer height works well.

---

## Run it locally

No server needed, and no internet connection required. Download the repo (or clone it) and open `index.html` in any modern browser — the 3D libraries live in `vendor/`, so everything runs from local files.

---

## Development notes

**Third-party libraries are vendored, not loaded from a CDN.** `vendor/` holds three.js 0.146.0, opentype.js 1.3.4, JSZip 3.10.1, and three.js's `SVGLoader`. Older versions pulled these from jsdelivr, which made the tool depend on a third-party host at load time. A user reported it coming up completely blank in Firefox — no label rows, the status frozen on "Loading…" — while it worked in Chrome: their browser was blocking the CDN (DNS-over-HTTPS, tracking protection, or an extension). Serving the libraries from the same origin removes that failure mode entirely; they can't be blocked without blocking the page itself. `.gitattributes` marks `vendor/**` as binary so Git leaves the minified files byte-for-byte.

**Startup fails safe.** `init()` builds the label form *before* initialising three.js, then verifies each library actually loaded and names any that didn't. A missing library or a WebGL failure now leaves a working form with a clear message instead of a dead page; the Download button stays disabled because nothing can be exported without three.js.

**Build-plate fields fit four digits.** They were previously narrow enough to clip a three-digit value, so a 250 mm plate showed as "25" — easily misread as centimetres. This affected every printer preset at or above 100 mm.

---

Part of the [GEN2 Modular Storage System](https://jerrari3d.com) by Jerrari3D.

## More from Jerrari3D

- 🌐 [jerrari3d.com](https://jerrari3d.com)
- 🟧 [Printables](https://www.printables.com/@Jerrari)
- 📦 [Thangs](https://thangs.com/designer/Jerrari)
