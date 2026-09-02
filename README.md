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

JSON files are marked `-text` in `.gitattributes`, preserving the bytes covered by hashes.

Repository scope is limited to Scene JSON and index metadata. Licenses, keys, executables, game clients, and media assets remain with their authorized sources.

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

Follow the [G4 export procedure](https://github.com/ImoutoHeaven/MuvluvUnlockCG/blob/main/docs/g4-scene-export-tutorial-zh.md). The promotion tool validates the export and synchronized corpus and requires a clean worktree. Maintainers control commit and push operations.

Maintainers update the offline distribution manually. Exported `scenes.json`, `manifest.json`, and `scene/` are published byte-for-byte.
