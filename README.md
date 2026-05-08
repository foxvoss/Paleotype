# Paleotype

Paleotype is a browser-based tool designed for the manual transcription of historical documents. It provides a split-screen interface to view digital surrogates (images or PDFs) while transcribing the text in a clean, distraction-free editor.

## Access

You can access the application at:
`https://foxvoss.github.io/Paleotype/`

## Local Usage (Offline)

Paleotype is fully portable and can be run without an internet connection:

1. **Download:** Save the `index.html` (or the self-contained `paleotype_embedded.html`) file to your local device.
2. **Run:** Open the file in any modern web browser.
3. **Privacy:** All processing remains local. No data ever leaves your device.

> **Android note:** Due to browser security restrictions, a standard HTML file cannot load images from the same local folder on Android. Use the self-contained embedded version (`paleotype_embedded.html`), which has all reference images bundled inside the file.

## Core Features

- **Format Support:** Compatibility with PDF, JPG, PNG, and WEBP files.
- **Image Enhancement:** Integrated controls for brightness, contrast, rotation, and an invert (negative) mode to improve legibility of faded or dark manuscripts.
- **Navigation:** Page-specific navigation for multi-page PDF documents, including a direct page-jump input.
- **No Automated Interference:** Spellcheck and auto-correct are disabled by default to prevent unintended alteration of archaic spelling, regional dialects, or paleographic notations.
- **Export Options:** Transcription data can be copied to the clipboard or downloaded as a plain text file (.txt) using UTF-8 encoding to preserve special characters and diacritics.
- **Multilingual Interface:** Available in English, Dutch, German, French, Spanish, and Italian.

## Reference Panel (Spiekbrief)

A collapsible middle panel can be opened between the document viewer and the transcription editor by clicking the book icon (📖) in the toolbar. This panel is intended as a palaeographic reference while transcribing.

- **Built-in references:** The Bogtman letter guide (A–M and N–Z) is included by default, based on *W. Bogtman — FAQ Genealogie BeNeLux*.
- **Custom images:** Additional reference images (e.g. alphabet charts, sample hands) can be loaded from your device using the 🖼 button. Multiple files can be selected at once; they are added to the dropdown list by filename.
- **Removing images:** User-added images can be removed from the list with the ✕ button. The built-in Bogtman references cannot be removed.
- **Pan and zoom:** The reference image supports drag-to-pan (one finger or mouse) and pinch-to-zoom (two fingers) or scroll-wheel zoom, identical to the main viewer. The − and + buttons also adjust zoom. The panel height is fixed so it does not push the other panels out of view.
- **Persistent visibility:** The reference panel stays visible while typing; it does not auto-hide when the editor receives focus.

## Image Viewer

- **Pan and zoom:** Drag to pan, pinch or scroll to zoom.
- **Filter panel:** Accessible via the droplet icon (💧) in the top-right corner of the viewer. Controls brightness, contrast, rotation, and negative mode. The panel opens below the icon without overlapping the rotation buttons.
- **Rendering:** The canvas is cleared and redrawn on each page load to prevent stale tile artefacts when zooming out on PDF documents. Filters are applied directly to the canvas/image element to avoid GPU compositing conflicts.

## Privacy and Security

- **Local Processing:** All file processing and text entry occur locally within the user's browser.
- **Persistence:** Text is automatically cached in the browser's local storage to prevent data loss during accidental refreshes.

## Instructions for Use

1. **Load Document:** Tap *Laden* to select an image or PDF from your device.
2. **Adjust View:** Use the filter panel (💧, top-right of viewer) to adjust brightness, contrast, rotation, or enable negative mode.
3. **Open Reference:** Tap the book icon (📖) to open the palaeographic reference panel between the viewer and the editor. Load your own reference images with the 🖼 button.
4. **Transcribe:** Enter text in the editor pane at the bottom.
5. **Export:** Use the export button to save your work or copy it to the clipboard.

## Changelog

### 2026-05-08
- **Reference panel added:** Collapsible middle panel between viewer and editor, toggled by the book icon in the toolbar.
- **Bogtman reference embedded:** Both Bogtman A–M and N–Z letter guides are bundled as Base64 data URIs inside the HTML file, eliminating the need for separate image files (required for Android local file usage).
- **Custom reference images:** Users can load one or more images from their device into the reference panel dropdown. Images are read as data URIs so no external files are needed.
- **Reference panel pan/zoom:** Full touch and mouse pan/zoom support on the reference image, identical in behaviour to the main viewer. Panel height stays fixed.
- **Reference panel stays open while typing:** Removed the auto-hide-on-editor-focus behaviour.
- **Filter panel repositioned:** Droplet icon moved back to top-right; filter panel opens directly below the icon (offset 60px from top) to avoid overlapping the rotation buttons.
- **Export button:** Text label hidden on narrow screens; icon only shown on mobile to prevent the toolbar from overflowing.
- **Black tile artefacts fixed:** Canvas is now explicitly cleared and filled white before each PDF page render, preventing stale GPU tile artefacts when zooming out.
- **Filters moved to element level:** CSS filters are now applied directly to the canvas or image element rather than to the transform layer, preventing compositing conflicts with `will-change: transform`.
- **Touch target sizes:** All reference panel buttons enlarged to 44×44 px minimum for reliable tapping on mobile.

## License

This project is open-source and available for personal, educational, and professional research use.
