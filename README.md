# MuvluvSceneFrames

Validated SceneFrame corpus exported through the licensed G4 runtime for use by MuvluvUnlockCG.

## Layout

```text
scenes.json
manifest.json
scene/<SceneId>/scene.json
```

- `scenes.json`: G4 WebView catalog.
- `manifest.json`: Scene ID, canonical path, byte count, SHA-256, and frame count.
- `scene/<SceneId>/scene.json`: original response bytes.

JSON files are marked `-text` in `.gitattributes` so Git does not change bytes covered by hashes.

## Corpus

| Metric | Value |
| --- | ---: |
| Scenes | 1,032 |
| Scene bytes | 160,509,906 |
| Commands | 293,249 |
| `muvluvFrame` commands | 87,383 |

This repository contains no license, key, executable, game client, or media asset.

## Static hosting

Serve the repository root unchanged over HTTPS. MuvluvUnlockCG requests only:

```text
<base>/manifest.json
<base>/scene/<numeric SceneId>/scene.json
```

MuvluvUnlockCG uses this GitHub raw root by default:

```text
https://raw.githubusercontent.com/ImoutoHeaven/MuvluvSceneFrame/main/
```

Another static HTTPS root may be configured.

## Update

Use `MuvluvUnlockCG/tools/g4_scene_export.py` to create a new output directory, validate it with `tools/http_cache_inventory.py` in Docker, then run `tools/promote_g4_scene_export.ps1` with `-Preview` before synchronization. The promotion tool requires a clean worktree and does not commit or push.

The offline distribution is updated manually. Exported `scenes.json`, `manifest.json`, and `scene/` are published without format conversion.
