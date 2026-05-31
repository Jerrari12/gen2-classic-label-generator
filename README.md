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

No server needed. Download `index.html` and open it in any modern browser. (It loads three.js, opentype.js, and JSZip from a CDN, so an internet connection is required the first time.)

---

Part of the [GEN2 Modular Storage System](https://jerrari3d.com) by Jerrari3D.

## More from Jerrari3D

- 🌐 [jerrari3d.com](https://jerrari3d.com)
- 🟧 [Printables](https://www.printables.com/@Jerrari)
- 📦 [Thangs](https://thangs.com/designer/Jerrari)
