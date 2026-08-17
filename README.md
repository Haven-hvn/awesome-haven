# Awesome Haven [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> Curated directory for **Haven — L7 (application-layer) sovereign media protocol**. Like HTTP is L7 for the web and Usenet was L7 for binaries, Haven is L7 for files-as-CIDs over Arkiv L3 (`0x44…0044`, `btl`/`regex` via `roaring64/ART`) + ICP VetKD (`haven-aol` `dciac-…qlzuq`) + Filecoin (IPFS `CID` only in Arkiv). Same file `CID`, many UIs around it — no private backend (`Datastores:0`).

## Contents
- [Protocol](#protocol)
- [Clients](#clients)
- [Interfaces — Many UIs Around Files](#interfaces--many-uis-around-files)
  - [Built — Exists Today](#built--exists-today)
  - [Proposed — To Build](#proposed--to-build)
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
Same `ipfs_cid`/`piece_cid` via Filecoin, `haven-aol` VetKD if `is_encrypted=1`, discovered via `arkiv_query(eq("gate_token",…))`. Each file `CID` can be rendered by many diverse GUIs — **Built vs Proposed** below.

### Built — Exists Today
Verified from `Haven-hvn/haven-dapp` (Decentralized Video Library — Next.js 16, Tailwind, wagmi/viem, Haven-AOL VetKD, IPFS/Filecoin via Arkiv SDK, `video/*` encrypted) and `Haven-hvn/haven-mobile` (Kotlin Compose/Media3/Room, `foc-cache`, offline-first viewer — also `video/*` via Media3):
- [Haven dapp — Video player](https://github.com/Haven-hvn/haven-dapp) - `mp4`/`mkv`/`mov` `video/*` — Web3 video streaming, wallet auth, VetKD decrypt, responsive + dark mode.
- [Haven mobile — Video player](https://github.com/Haven-hvn/haven-mobile) - `mp4`/`mkv` `video/*` — Android Media3 playback, offline-first `foc-cache`, same `CID` as dapp.
- [Haven CLI — Archival pipeline](https://github.com/Haven-hvn/haven-cli) - `mp4`/`mkv` `video/*` — `arkiv_sync.py` encrypt + pin to Filecoin (exists, video-only).

*All built clients today are `video/*`-only. No built client yet for audio, images, documents, datasets, code, 3D or archives beyond video.*

### Proposed — To Build
Many file types, many diverse GUIs on the **same CID** per category — not yet built, open for contributors. Each DataDAO can ship its own GUI:

**Video & Film** — `mp4, mkv, mov, webm, avi, m4v, mpg`:
- [Timeline suite](https://github.com/Haven-hvn/docs/blob/main/architecture/02-haven-dapp.md#timeline) - Timeline viewer, chapter navigator and clip extractor.
- [Studio tools](https://github.com/Haven-hvn/haven-cli#studio) - Thumbnail storyboarder, subtitle editor and transcoder.

**Audio** — `mp3, flac, wav, m4a, ogg, opus, aiff, gp5, psarc`:
- [Music & podcasts](https://github.com/Haven-hvn/docs/blob/main/architecture/03-haven-cli.md#music) - Haven player, podcast app and waveform viewer.
- [Stems & practice](https://github.com/Haven-hvn/haven-mobile#stems) - Mixer, stem splitter, practice looper and loudness analyzer.
- [Guitar & tabs](https://github.com/Haven-hvn/foc-local-first-android#guitar) - `psarc`/`gp5` tab viewer, extractor and stem splitter — one audio subtype among many.

**Images & Photography** — `jpg, png, raw, tiff, heic, webp, avif, geojson`:
- [Photo galleries](https://github.com/Haven-hvn/haven-mobile#photo) - Gallery, lightbox and EXIF editor — offline-first.
- [Maps & GIS](https://github.com/Haven-hvn/docs/blob/main/architecture/04-haven-mobile.md#maps) - Map viewer, tile renderer and coordinate inspector.

**Documents & Publishing** — `pdf, epub, md, docx, djvu, cbz, html`:
- [Ebook readers](https://github.com/Haven-hvn/docs#ebook) - `epub.js`/`pdf.js` viewers, Readium and `haven-cli` ebook converter.
- [Research suite](https://github.com/Haven-hvn/docs/blob/main/entities/MEDIA_CONTENT_SPEC.md#research) - Reader, citation graph, annotation layer and text-to-speech.

**Datasets & Research** — `csv, parquet, jsonl, hdf5, fits, tsv, arrow`:
- [Open datasets](https://github.com/Haven-hvn/data-utils#datasets) - Table viewer, query console and chart builder.
- [Science archives](https://github.com/Haven-hvn/haven-provenance) - Provenance viewer, lineage graph and attestation checker.

**Code & Models** — `zip, tar, safetensors, onnx, pt, wasm, gguf`:
- [Model weights](https://github.com/Haven-hvn/haven-core#weights) - Model loader, inference runner and provenance card.
- [WebAssembly playground](https://github.com/Haven-hvn/haven-lander#wasm) - WebAssembly runner, sandbox preview and dependency inspector.

**3D & Spatial** — `gltf, glb, obj, fbx, usdz, stl, psarc, pak`:
- [3D assets](https://github.com/Haven-hvn/haven-lander#3d) - 3D viewer, AR preview and scene composer.
- [Game mods](https://github.com/Haven-hvn/foc-local-first-android#mods) - Mod manager, dependency resolver and in-game overlay — `psarc` now one 3D mod type.

**Archives & Collections** — `zip, tar, 7z, iso, bagit, json`:
- [Time capsules](https://github.com/Haven-hvn/humanactivitygathering) - Collection browser, timeline scrubber and `btl` expiry inspector.
- [Agent swarms](https://github.com/Haven-hvn/haven-agent) - Swarm viewer, `VetKD` decrypt and replay console.

## Concepts
Haven is L7 (application layer) — the user-facing media layer, like HTTP is L7 for the web and Usenet was L7 for binaries — composing Arkiv L3, ICP VetKD and Filecoin underneath. `alt.binaries for DataDAOs`: a private-tracker replacement that is token-gated, sealed and permanently pinned. Files are CIDs: entity headers are ephemeral (`btl`/`EXPIRE`), bodies are durable (Filecoin `PDPVerifier`), so any DataDAO can ship its own GUI around the same file.

## Planet Visualization
Interactive orbit view of composable permissionless networks: [planet/index.html](planet/index.html) — Haven L7 at center, Arkiv L3, ICP VetKD, EVM, Filecoin as orbits, many UIs around one file CID. No private backend — only CIDs + eth_call + ecrecover.

## Contributing
PRs welcome! Each DataDAO may ship its own GUI around the same file protocol. See `awesome.md` and `interfaces/README.md`. Please follow [awesome guidelines](https://github.com/sindresorhus/awesome/blob/main/pull_request_template.md).
