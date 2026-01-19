20260119113553
# RFC: Flexible Configuration and Overrides

## Staging
ZID: 20260119113553
New File: `config.json`
Updated File: `goldendict-tts.py`

## Implementation Details

### Analytics
- **Decoupling**: The previous implementation had hardcoded relative paths to the Anki addon. This made it difficult to move the GoldenDict script to a different location or share it across environments.
- **Override Mechanism**: Created a two-tier configuration system. The script first loads a donor configuration (from the Anki addon) and then merges it with local overrides. This allows the GoldenDict process to use different engine priorities or cache paths without modifying the shared Anki setup.

### Decisions
1. **Local Config**: Added `config.json` in the script's own directory.
2. **Merge Pattern**: Implemented a key-based override in `load_config()`. The `anki_addon_path` determines the source of truth for the base configuration.
3. **Graceful Fallback**: If `config.json` is missing, the script defaults to the previous hardcoded paths to ensure zero-config backward compatibility during migration.
