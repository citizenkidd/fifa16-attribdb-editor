# FIFA 16 AttribDB Editor

Offline browser editor for FIFA 16 `attribdb` and `attribdbgameplay` files.

## Download

Download the current package from the
[GitHub Releases page](https://github.com/citizenkidd/fifa16-attribdb-editor/releases).

Extract the complete ZIP, keep all files together (including
`editor-styles.css` beside `attribdb_editor_final_v2.html`), and open the HTML
file in a modern desktop browser.

## Features

- Built-in FIFA 16 schemas and exact verification of user-supplied originals
- Optional remembered originals folder in supporting browsers
- Automatic AttribDB and AttribDB Gameplay presets
- Validation before imported BIN/VLT pairs replace the active session
- Compact evidence controls and a Research Mode drawer for maintaining field
  notes, confidence, increase/decrease behavior, and sources
- Browser-local research autosave with JSON backup and Sheet-compatible CSV
  import/export
- Numeric, Boolean, array, vector, matrix, text, and curve viewers/editors
- Original-versus-working comparison and per-value revert
- Dedicated Changes workspace grouped by folder and file, with original-to-current summaries and exact field-level revert
- Navigator search for files and schema fields, modified/evidence filters, and
  visible change counts
- Keyboard-accessible tree navigation with remembered folder expansion and
  sidebar sizing
- Standardized scalar, Boolean, vector, matrix, and read-only text field rows
  with baseline, revert, deviation, and validation feedback
- Compound Boolean, float, vector, and fixed eight-point curve arrays with
  collapsed summaries, validated editors, original comparisons, and group/item
  revert controls
- Preset-derived **Export Mod Files** without overwriting imported files
- Dependency-free accessible tooltips for static and dynamically rebuilt controls,
  with a persistent **Hover tooltips** preference (off by default)
- Modular dependency-free architecture: the runtime is split into
  TypeScript-checked UMD service/controller modules with no build step or
  runtime network dependency
- Strict staged field-value validation before any byte is written
- Fully client-side operation

## Start editing

Open the editor and follow the setup surface: choose AttribDB or AttribDB
Gameplay, verify the matching original BIN/VLT pair, then optionally load an
existing mod. The application bar identifies the current project and
clean/unsaved state; infrequent preset, originals, mod-loading, and Research
actions are grouped under **Project & tools**. Use **Export Mod Files** to
download the modified pair.

After loading a project, search the navigator by logical file or field name.
Use the modified-only and evidence filters together, inspect the **Changes**
workspace to review fields modified from the verified originals, open an exact
field in the editor, or revert that complete field. Exporting mod files updates
the saved snapshot but leaves modifications visible in Changes until they match
the originals. Use Previous/Next controls to move between matching editor rows.

Ordinary fields share a consistent identity/value/baseline/action layout.
Invalid or non-finite numeric input is rejected before it reaches the working
buffers; integer machine bounds are enforced and any clamping is communicated.
Float32 display preserves signed zero, signed infinity, and NaN payload bits;
applying a zero-percent adjustment to `-0` does not normalize it to `+0`. A
float32 field whose value is positive zero renders as `0` in the numeric input
instead of a blank field; the semantic `+0`/`-0` formatting is preserved.
Compound arrays preserve their eight-byte headers and use the same validation,
modified-count, baseline, and revert behavior. Curve fields show current and
original lines with textual labels; unusual bounds or descending points are
reported as warnings without silently rewriting the data.

JSON imports validate all mapped values before changing a file. A current-file
import is all-or-nothing; folder imports keep valid files while reporting each
rejected file without partially applying it.

Optionally choose **Remember Originals Folder** and select a root folder laid
out like this:

```text
root/
├── attribdb/attribdb.bin + attribdb.vlt
└── attribdbgameplay/attribdb.bin + attribdb.vlt
```

Supporting browsers remember the approved folder and reuse it when permission
allows. Otherwise, choose AttribDB or AttribDB Gameplay and manually select the
matching pair from your own FIFA 16 installation or backup. Files are verified
locally. The release does not include FIFA database files.

Folder JSON ZIP export works offline and is generated locally; no internet
connection is required for any editor runtime feature.

Actions, inputs, status badges, and technical controls can provide concise
supplementary tooltips on hover and keyboard focus. They are off by default;
open **Project & tools → Preferences** to enable **Hover tooltips**. The choice
is remembered locally without requiring a reload and works when the HTML is
opened directly through `file://`. The same tooltip behavior works after the
navigator, editor, Changes, and Research surfaces are rebuilt.
Hover tooltips appear after 1000 ms; keyboard-focus tooltips appear after 200 ms.

See [SUPPORT.md](SUPPORT.md) when reporting a problem.

## License

This project is source-available under the
[PolyForm Noncommercial License 1.0.0](LICENSE.md). You may use, modify, and
redistribute it for noncommercial purposes, subject to the license and
[required notices](NOTICE.md). Commercial use, monetization, and selling the
tool or derivatives are not permitted.
