# StudyPilot

StudyPilot is a Chrome/Edge Manifest V3 browser extension for Chinese native students studying English technical materials. It helps users select text on any webpage, view a bilingual learning popup, and save notes locally.

## Download

Download the complete extension package from this repository:

- `dist/StudyPilot-1.0.0.zip`

The ZIP contains the full project source, including `manifest.json`, JavaScript, CSS, HTML, docs, and PNG icons.

## Install From ZIP

1. Download `dist/StudyPilot-1.0.0.zip`.
2. Extract the ZIP file.
3. Open Chrome or Edge extensions page:
   - Chrome: `chrome://extensions`
   - Edge: `edge://extensions`
4. Enable Developer Mode.
5. Click **Load unpacked**.
6. Select the extracted `StudyPilot-1.0.0` folder.

## What It Does

- Shows an **Explain** button when webpage text is selected.
- Displays original text, Chinese explanation, English explanation, and vocabulary.
- Saves notes locally with `chrome.storage.local`.
- Includes a popup page for searching/deleting notes.
- Includes an options page for language mode and difficulty.

## Safety Notes

This project is for normal learning and reading assistance only. It does not include cheating, exam bypassing, screen-monitor evasion, stealth automation, credential collection, remote code execution, or hidden network requests.

## Known Limitations

- v1 uses local rule-based explanations, not AI-quality translation.
- No backend or paid API is required.
- It does not run on restricted browser pages like `chrome://` pages or the Chrome Web Store.
