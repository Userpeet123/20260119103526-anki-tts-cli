20260119115317
# RFC: Naming Appropriateness

## Staging
ZID: 20260119115317
Reference: `20260119103526-goldendict-tts`

## Analysis
The current repository name and script name (`goldendict-tts.py`) imply that the tool is strictly for GoldenDict integration. However, the implementation has evolved into a generic CLI wrapper for the Anki TTS engine that is:
1. **Client Agnostic**: Works with GoldenDict, AutoHotkey, Terminal, or any process spawner.
2. **Feature Rich**: Handles rotation, caching, and fallback logic independently of the caller.

## Conclusion
The name `goldendict-tts` is **too specific** and potentially misleading. A more accurate name would describe the tool's function (CLI) and its engine (Anki TTS), rather than one specific client.

## Recommendation
**`anki-tts-cli`** is the most appropriate name.
- It accurately describes the tool: A CLI for Anki TTS.
- It is neutral regarding the client (GoldenDict vs AHK).

*Note: Renaming the root repository folder `20260119103526-goldendict-tts` is often difficult in active workspaces, but the script `goldendict-tts.py` can be renamed to `anki-tts-cli.py` to reflect its universal nature.*
