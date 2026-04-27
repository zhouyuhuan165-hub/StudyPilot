# StudyPilot

StudyPilot is a Chrome/Edge Manifest V3 browser extension for Chinese native students reading English technical materials. Select text on any webpage, click **Explain**, and StudyPilot shows a bilingual learning popup with the original text, simple Chinese and English explanations, key vocabulary, and local note saving.

This project is for normal learning and reading assistance only. It does not include cheating, exam bypassing, screen-monitor evasion, stealth automation, credential collection, or hidden network requests.

## Install on Windows

1. Open the extensions page:
   - Chrome: `chrome://extensions`
   - Edge: `edge://extensions`
2. Enable **Developer Mode**.
3. Click **Load unpacked**.
4. Select this project folder: `C:\Users\32784\Documents\New project`.

## Install on macOS

1. Download the project or the macOS package from `dist/StudyPilot-mac-1.0.0.zip`.
2. Extract the ZIP file in Finder.
3. Open the extensions page:
   - Chrome: `chrome://extensions`
   - Edge: `edge://extensions`
4. Enable **Developer Mode**.
5. Click **Load unpacked**.
6. Select the extracted `StudyPilot-mac-1.0.0` folder.

StudyPilot works on macOS in Chrome and Edge because it is a standard Manifest V3 extension. Safari is not supported by this package.

## Use

1. Open a regular webpage with English technical text.
2. Select at least two characters.
3. Click the floating **Explain** button.
4. Review the popup explanation and vocabulary.
5. Click **Save note** to save the note locally.
6. Click the StudyPilot extension icon to view, search, delete, or clear saved notes.
7. Open **Options** to choose language mode and difficulty level.

## File Structure

```text
StudyPilot/
|-- manifest.json
|-- background.js
|-- content.js
|-- content.css
|-- popup.html
|-- popup.js
|-- popup.css
|-- options.html
|-- options.js
|-- options.css
|-- README.md
|-- MAC_INSTALL.md
|-- AGENTS.md
`-- icons/
    |-- icon16.png
    |-- icon48.png
    `-- icon128.png
```

## How Explanations Work in v1

StudyPilot v1 uses local rule-based logic in `background.js`. It extracts likely technical vocabulary, gives short heuristic explanations, and stores notes using `chrome.storage.local`.

No paid API key is required. No external backend is used.

## Later OpenAI API Integration

`background.js` includes a placeholder function:

```js
async function generateExplanationWithAI(text, settings) {
  return generateExplanationLocally(text, settings);
}
```

To connect an OpenAI API later, keep the same return shape:

```js
{
  originalText,
  chineseExplanation,
  englishExplanation,
  vocabulary: [
    { word, chinese, english }
  ],
  createdAt
}
```

Recommended future approach:

1. Add an options field for the API provider or endpoint only after deciding how keys should be handled safely.
2. Replace the placeholder internals with a secure API call.
3. Keep note storage local unless the user explicitly adds a sync feature.
4. Never add hidden network requests.

## Known Limitations

- Explanations are heuristic and may be incomplete or awkward.
- The local vocabulary dictionary is small.
- The extension cannot run on browser-restricted pages such as `chrome://` pages or the Chrome Web Store.
- Copying may be unavailable on some insecure pages if the browser blocks clipboard access.
- Notes are stored locally in the browser profile, not synced to a server.
- The separate macOS package is still a Chrome/Edge extension package, not a native `.dmg` app.
- Safari requires separate extension conversion work and is not included in v1.
