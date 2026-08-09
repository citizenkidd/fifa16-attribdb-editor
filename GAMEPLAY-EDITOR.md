# FIFA 16 Gameplay Editor

The release includes a generated Cheat Engine table for the FIFA 16 runtime
Gameplay Editor. Cheat Engine is an external prerequisite and is not bundled
with this package.

## Normal workflow

1. Start FIFA 16 and reach a game state where the gameplay runtime is loaded.
2. Open `fifa16-gameplay-editor.ct` in Cheat Engine.
3. Enable **Gameplay Editor** and allow the one-time runtime indexing to finish.
   Wait until the editor reports **Ready**.
4. Select a mapped class, collection, and field, then use **Edit value...** or
   one of the percentage controls.
5. Some changes take effect only after restarting the match.
6. Use **Restore selected** or **Restore All** before closing when appropriate.

The `.CT` already embeds the matching Lua backend, so it is the only file that
normally needs to be opened. The standalone
`fifa16-attribsys-runtime.lua` is included for transparency, diagnostics, and
advanced manual use; it normally does not need to be loaded separately.

Runtime mappings are scoped to the current FIFA process and session. If FIFA
restarts, close the old table session and enable or reindex the editor again so
the new process is indexed.

This package contains no FIFA database, game executable, or other game files.
