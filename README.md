# FIFA 16 AttribDB Editor

Offline browser editor for FIFA 16 `attribdb` and `attribdbgameplay` files.

## Download

Download the current package from the
[GitHub Releases page](https://github.com/citizenkidd/fifa16-attribdb-editor/releases).

Extract the complete ZIP, keep all files together, and open
`attribdb_editor_final_v2.html` in a modern desktop browser.

## Features

- Built-in FIFA 16 schemas and exact verification of user-supplied originals
- Optional remembered originals folder in supporting browsers
- Automatic AttribDB and AttribDB Gameplay presets
- Validation before imported BIN/VLT pairs replace the active session
- Numeric, Boolean, array, vector, matrix, text, and curve viewers/editors
- Original-versus-working comparison and per-value revert
- Save All export without overwriting imported files
- Fully client-side operation

## Start editing

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

## Current limitation

Modified JSON export is not reliable in this preview. The main BIN/VLT editing
and Save All workflow is separate from that feature.

See [SUPPORT.md](SUPPORT.md) when reporting a problem.

## License

This project is source-available under the
[PolyForm Noncommercial License 1.0.0](LICENSE.md). You may use, modify, and
redistribute it for noncommercial purposes, subject to the license and
[required notices](NOTICE.md). Commercial use, monetization, and selling the
tool or derivatives are not permitted.
