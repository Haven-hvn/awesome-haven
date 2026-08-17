# Awesome Haven [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> Curated directory for **Haven — L7 sovereign media protocol**. Files as CIDs: Arkiv OP L3 (`0x44…0044` ephemeral entities, `btl`/`regex` via `roaring64/ART`) + ICP VetKD (`haven-aol` `dciac-…qlzuq`, `gate_token/gate_chain/gate_threshold` per `cid/epoch`) + Filecoin Onchain Cloud (IPFS `CID` only in Arkiv). Many UIs around the same file pointer — no private backend (`Datastores:0`).

## Contents
- [Protocol](#protocol)
- [Clients](#clients)
- [Interfaces — Many UIs Around Files](#interfaces--many-uis-around-files)
  - [Video & Film](#video--film)
  - [Audio](#audio)
  - [Images & Photography](#images--photography)
  - [Documents & Publishing](#documents--publishing)
  - [Datasets & Research](#datasets--research)
  - [Code & Models](#code--models)
  - [3D & Spatial](#3d--spatial)
  - [Archives & Collections](#archives--collections)
- [Concepts](#concepts)
- [Planet Visualization](#planet-visualization)

## Protocol
- [Haven docs](https://github.com/Haven-hvn/docs) - Living architecture, `WEB3_PARADIGM`, `ENTITY_SHAPE` (`Ident32`/`Mime128`/`btl` at `0x44…0044`), `MEDIA_CONTENT_SPEC` (`CID`-only body).
- [haven-aol](https://github.com/Haven-hvn/haven-aol) - Always Online, ICP-native VetKD gating for DAOs, DataDAOs and agent swarms.
- [arkiv-op-reth](https://github.com/Haven-hvn/docs/blob/main/architecture/05-arkiv-chain.md) - Arkiv OP L3 reth reference (`just node-dev` 1337 or `braga.hoodi.arkiv.network/rpc` or both).

## Clients
Reference thin clients obeying the same file-CID rule set:

- [haven-dapp](https://github.com/Haven-hvn/haven-dapp) - TypeScript/Next.js 15 Web3 frontend (`arkiv_query`, decrypt and playback).
- [haven-cli](https://github.com/Haven-hvn/haven-cli) - Python 3.11+ media pipeline (`arkiv_sync.py`), encryption and archival — *Reclaiming the Internet for the User*.
- [haven-mobile](https://github.com/Haven-hvn/haven-mobile) - Kotlin Compose/Media3/Room, offline-first with `foc-cache`.
- [foc-local-first-android](https://github.com/Haven-hvn/foc-local-first-android) - Kotlin/Android 3-path retrieval (direct SP `/piece`, FilBeam CDN, IPFS) hedged race, LRU/TTL.

## Interfaces — Many UIs Around Files
Same `ipfs_cid`/`piece_cid` via Filecoin, `haven-aol` VetKD if `is_encrypted=1`, discovered via `arkiv_query(eq("gate_token",…))`. Each category shows **many file types, many diverse GUIs on the same CID**.

### Video & Film
File types `mp4, mkv, mov, webm, avi, m4v, mpg` — same CID, diverse GUIs:
- [Cinema players](https://github.com/Haven-hvn/haven-dapp) - Haven Web player, `mpv`/`vlc` wrappers and mobile Media3 player.
- [Timeline suite](https://github.com/Haven-hvn/docs/blob/main/architecture/02-haven-dapp.md) - Timeline viewer, chapter navigator and clip extractor.
- [Studio tools](https://github.com/Haven-hvn/haven-cli) - Thumbnail storyboarder, subtitle editor and transcoder.

### Audio
File types `mp3, flac, wav, m4a, ogg, opus, aiff, gp5, psarc` — same CID, diverse GUIs:
- [Music & podcasts](https://github.com/Haven-hvn/docs/blob/main/architecture/03-haven-cli.md) - Haven player, podcast app and waveform viewer.
- [Stems & practice](https://github.com/Haven-hvn/haven-mobile) - Mixer, stem splitter, practice looper and loudness analyzer.
- [Guitar & tabs](https://github.com/Haven-hvn/foc-local-first-android) - `psarc`/`gp5` tab viewer, `psarc` extractor and stem splitter — one audio subtype among many.

### Images & Photography
File types `jpg, png, raw, tiff, heic, webp, avif, geojson` — same CID, diverse GUIs:
- [Photo galleries](https://github.com/Haven-hvn/haven-mobile) - Gallery, lightbox and EXIF editor — offline-first via `foc-cache`.
- [Maps & GIS](https://github.com/Haven-hvn/docs/blob/main/architecture/04-haven-mobile.md) - Map viewer, tile renderer and coordinate inspector.
- [Darkroom](https://github.com/Haven-hvn/data-utils) - RAW developer, panorama stitcher and color grader.

### Documents & Publishing
File types `pdf, epub, md, docx, djvu, cbz, html` — same CID, diverse GUIs:
- [Ebook readers](https://github.com/Haven-hvn/docs) - `epub.js`/`pdf.js` viewers, Readium and `haven-cli` ebook converter — same `encrypted_cid` and epoch.
- [Research suite](https://github.com/Haven-hvn/docs/blob/main/entities/MEDIA_CONTENT_SPEC.md) - Reader, citation graph, annotation layer and text-to-speech.

### Datasets & Research
File types `csv, parquet, jsonl, hdf5, fits, tsv, arrow` — same CID, diverse GUIs:
- [Open datasets](https://github.com/Haven-hvn/data-utils) - Table viewer, query console and chart builder.
- [Science archives](https://github.com/Haven-hvn/haven-provenance) - Provenance viewer, lineage graph and attestation checker.
- [Lab notebooks](https://github.com/Haven-hvn/haven-core) - Jupyter bridge, version diff and dataset card.

### Code & Models
File types `zip, tar, safetensors, onnx, pt, wasm, gguf` — same CID, diverse GUIs:
- [Model weights](https://github.com/Haven-hvn/haven-core) - Model loader, inference runner and provenance card.
- [Code bundles](https://github.com/Haven-hvn/haven-adapters) - Code viewer, diff viewer and adapter registry.
- [WASM playground](https://github.com/Haven-hvn/haven-lander) - WASM runner, sandbox preview and dependency inspector.

### 3D & Spatial
File types `gltf, glb, obj, fbx, usdz, stl, psarc, pak` — same CID, diverse GUIs:
- [3D assets](https://github.com/Haven-hvn/haven-lander) - 3D viewer, AR preview and scene composer.
- [Game mods](https://github.com/Haven-hvn/foc-local-first-android) - Mod manager, dependency resolver and in-game overlay — `psarc` now one 3D mod type among many.

### Archives & Collections
File types `zip, tar, 7z, iso, bagit, json` (swarm logs) — same CID, diverse GUIs:
- [Time capsules](https://github.com/Haven-hvn/humanactivitygathering) - Collection browser, timeline scrubber and `btl` expiry inspector.
- [Agent swarms](https://github.com/Haven-hvn/haven-agent) - Swarm viewer, `VetKD` decrypt and replay console.
- [Dedup & attestation](https://github.com/Haven-hvn/haven-provenance) - Dedup viewer, attested-publisher filter and `btl` reaper.

## Concepts
Haven L7 is `alt.binaries for DataDAOs` — a private-tracker replacement that is token-gated, sealed and permanently pinned. Files are stored as CIDs: entity headers are ephemeral (`btl`/`EXPIRE`), bodies are durable (Filecoin `PDPVerifier`).

## Planet Visualization
Interactive orbit view of composable permissionless networks: [planet/index.html](planet/index.html) — Haven L7 at center, Arkiv L3, ICP VetKD, EVM, Filecoin as orbits, many UIs around one file CID. No private backend — only CIDs + eth_call + ecrecover.

## Contributing
PRs welcome! Each DataDAO may ship its own GUI around the same file protocol. See `awesome.md` and `interfaces/README.md`. Please follow [awesome guidelines](https://github.com/sindresorhus/awesome/blob/main/pull_request_template.md).
