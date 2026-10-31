# MS Classic EXP Tracker

Track your EXP gained, EXP per hour, and estimated time to your next level in MapleStory Classic.

## Download the full Windows app

### [Download MSClassicExpTracker-1.0.1-windows-x64.zip (about 63 MB)](https://github.com/ilovepizza90001-bot/msclassic_exp_tracker_releases/releases/download/v1.0.1/MSClassicExpTracker-1.0.1-windows-x64.zip)

[View the latest release](https://github.com/ilovepizza90001-bot/msclassic_exp_tracker_releases/releases/latest)

The full app is in the ZIP linked above, including Python and its required Python packages. No GitHub account is required.

**Do not use the green Code → Download ZIP button or the Source code downloads.** Those download this repository's documentation, not the Windows app. On a release page, choose the asset whose name starts with `MSClassicExpTracker-` and ends with `-windows-x64.zip`. You do not need to download `update.json` or `update.json.sig` manually.

## Requirements

- Windows 10 or 11, 64-bit x64.
- Windows English (United States) OCR. If it is missing, follow [Microsoft's OCR language installation instructions](https://learn.microsoft.com/en-us/windows/powertoys/text-extractor#install-an-ocr-language-pack). PowerToys itself is not required.
- The game must be visible in the foreground with its bottom level and EXP HUD unobstructed.

## Install and start

1. Download the full app ZIP using the link above.
2. Right-click the downloaded ZIP and choose **Extract All**. Choose a folder you can write to.
3. Open the extracted folder. You should see `MSClassicExpTracker.exe` and an `_internal` folder. Keep them together; do not move just the EXE.
4. Open `MSClassicExpTracker.exe`. Administrator access is not required.
5. Click **Start**, then switch back to MapleStory and keep the bottom HUD visible.
6. Allow up to a few 10-second checks for the first confirmed level and EXP reading. EXP/hour and the time estimate appear after EXP gains are measured.

## What it tracks

- Automatically reads your level and EXP from the visible game HUD every 10 seconds.
- Shows recent EXP/hour over up to five active minutes, a session average, and an estimated time to the next level.
- Auto-pauses active time after 30 seconds of clear readings with no EXP gain, and resumes when EXP increases.
- Keeps the last accepted reading while retrying unclear readings. Rates and time estimates depend on successful HUD readings.

## Updates

The app checks for updates at startup. You can also click **Updates** in the tracker. You choose when to download and restart. Update downloads are verified using signed metadata and a SHA-256 checksum. Keep the original extracted app folder; its launcher opens your installed update.

## HUD calibration (version 1.0.1)

Automatic detection now supports more HUD sizes and preserves tinted/softened digits. If reading still fails:

1. Click **Start**, return to the foreground game, and wait at least 10 seconds so the tracker has a captured frame.
2. Click **Calibrate HUD** in the tracker.
3. Draw a tight box around the **level digits only**, then a second box around the **current EXP digits only**. Exclude the EXP label, brackets, and percentage.
4. Return to the game and wait for the next reading.

Only region coordinates are saved locally, not screenshots. Click **Auto** to clear the calibration. Recalibrate after a HUD layout or game aspect-ratio change. This expands compatibility but does not guarantee every layout.

## Troubleshooting

- **Only a README after extracting:** you downloaded the repository/source ZIP. Use the full app download link above.
- **Waiting for a clear reading or level reading:** return focus to the game, close menus covering the bottom HUD, and wait for the next check. Other fonts, HUD layouts, and scales may need additional calibration.
- **Missing Python/DLL files:** extract the entire ZIP and keep `_internal` beside the EXE. Running directly inside the ZIP or copying only the EXE will not work.
- **Windows publisher warning:** this release does not have a Windows Authenticode publisher certificate. Verify that your download came from this repository's Releases page. Signed update metadata is separate from Windows publisher signing.
- **Still having trouble:** report your Windows version, game resolution, tracker version, and exact error. Local diagnostics are in `%LOCALAPPDATA%\MSClassicExpTracker`, including `reading-diagnostics.json`, `tracker-error.log`, and `update-error.log` when present. Review files for personal information before sharing; never share private keys or GitHub tokens.

## Privacy and safety

The tracker reads the screen; it does not send game inputs, read game memory, or inject into the game. Normal screenshots stay in memory, and the app does not upload gameplay screenshots, EXP readings, or logs. Update requests contact GitHub. Session data and diagnostics are stored locally in `%LOCALAPPDATA%\MSClassicExpTracker`.

This is an unofficial tool, not endorsed by Nexon. No software can promise zero security risk or guarantee a game's account-enforcement decisions. Source code is maintained separately; this public repository hosts the app downloads and instructions.
