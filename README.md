# Demo Voice Pack

[简体中文](README.zh-cn.md) | English

A two-event demo voice pack for the VIR Signals editor extension — and the template you copy to make your own pack.

## What this pack is

It maps exactly two slots: `error` (played on error lines; this shared slot also covers errorAtPosition, noInlayHints and terminalCommandFailed) and `save` (played on manual save). Everything else keeps the editor's original sound — that is deliberate: a pack only replaces what it maps. `sourceLicense` is set to `third-party-cc0` because the audio comes from Kenney; the pack carries the attribution in `SOURCE.txt`.

## Hear it

1. Install the VIR Signals extension.
2. Run **VIR: Open Voice Packs Folder** and drop the `pack/` folder from this repository into it (or clone this repository straight into the packs folder).
3. Run **VIR: Select Voice Pack**, pick *Demo save+err*, and apply.
4. Trigger an error line and hit save — both sounds now come from this pack.

## Make it your own pack (the core section)

1. **Copy this repository.** The pack itself lives in `pack/` — that directory is the pack; everything else is documentation.
2. **Change `id`** in `pack/manifest.json` to your pack name: lowercase, hyphen-separated, unique in the universe (`my-cool-pack`).
3. **Change `name`, `version`, `author`** — `name` shows in the pack picker, keep it short (14 characters or fewer fits the status bar).
4. **Swap the audio** in `pack/sounds/` with your own WAV/MP3 files. Limits: ≤20MB per file, ≤2 seconds recommended (progress sounds ≤1s). Use all-lowercase filenames and make sure the paths in the manifest match the actual filenames **character by character, including case** — on Linux a case mismatch simply fails to find the file.
5. **Map the slots** in `manifest.json`: keys are slot names. The 28 slots: error, warning, break, quickFixes, taskCompleted, taskFailed, voiceRecordingStarted, voiceRecordingStopped, save, format, clear, progress, foldedAreas, confetti, terminalBell, terminalCommandSucceeded, diffLineInserted, diffLineModified, diffLineDeleted, chatEditModifiedFile, chatUserActionRequired, codeActionTriggered, codeActionApplied, editsKept, editsUndone, nextEditSuggestion, requestSent, responseReceived (this one also accepts numbered sub keys responseReceived1–4). A shared slot like `error` changes the sound of every event it carries. Slots you do not map keep the original sound — two slots is a complete pack.
6. **Fill `license` and `sourceLicense` honestly.** `sourceLicense` declares where the audio came from: `original` (you made it), `game-asset`, `third-party-cc0`, or `unknown`. Add a `SOURCE.txt` when the source asks for attribution.

## Publish

Push your pack repository to your own GitHub, copy the full 40-character commit SHA you want to release, then submit an entry to the registry following its CONTRIBUTING — one JSON file pointing at your repository at that SHA.

## Audio source

The two sounds are from **Kenney Interface Sounds** by Kenney Vleugels (kenney.nl), released under **CC0 1.0**. Attribution is not required but this pack ships it anyway — see `pack/SOURCE.txt`.
