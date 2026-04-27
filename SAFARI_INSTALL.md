# StudyPilot on Safari

StudyPilot can be tested in Safari on macOS as a Safari Web Extension package. This folder and ZIP are meant for temporary installation in Safari during testing.

## Files for Safari users

- `dist/StudyPilot-safari-1.0.0.zip`: Safari testing package
- `dist/StudyPilot-safari-1.0.0/`: Extracted Safari testing folder

## Temporary install in Safari on macOS

1. Open Safari.
2. Go to `Safari > Settings > Advanced`.
3. Enable **Show features for web developers** if the Developer tab is hidden.
4. Open `Safari > Settings > Developer`.
5. Click **Add Temporary Extension...**
6. Select `StudyPilot-safari-1.0.0.zip` or the extracted `StudyPilot-safari-1.0.0` folder.
7. Enable the extension in Safari if Safari asks for confirmation.

## Important notes

- This temporary installation is for testing and evaluation.
- Safari removes temporary extensions after 24 hours or when Safari quits.
- For long-term distribution, App Store release, or a signed installable Safari app, package the extension with Xcode on a Mac or use Safari Web Extension Packager in App Store Connect.
- This project does not include a native `.app` or `.dmg` because those final packaging steps require Apple tooling.

## Recommended next step for a formal Safari release

On a Mac with Xcode installed, run:

```bash
xcrun safari-web-extension-packager /path/to/StudyPilot-safari-1.0.0
```

That creates an Xcode project for a Safari Web Extension app container that you can sign, test, and distribute.
