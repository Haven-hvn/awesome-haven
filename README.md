# Awesome Haven [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> Curated directory for **Haven — L7 sovereign media protocol**. Files as CIDs: Arkiv OP L3 (`0x44…0044` ephemeral entities, `btl`/`regex` via `roaring64/ART`) + ICP VetKD (`haven-aol` `dciac-…qlzuq`, `gate_token/gate_chain/gate_threshold` per `cid/epoch`) + Filecoin Onchain Cloud (IPFS `CID` only in Arkiv). Many UIs around the same file pointer — no private backend (`Datastores:0`).

## Contents
- [Protocol](#protocol)
- [Clients](#clients)
- [Interfaces — Many UIs Around Files](#interfaces--many-uis-around-files)
  - [Audio — Music & Guitar](#audio--music--guitar)
  - [Documents — Ebooks](#documents--ebooks)
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
Same `ipfs_cid`/`piece_cid` via Filecoin, `haven-aol` VetKD if `is_encrypted=1`, discovered via `arkiv_query(eq("gate_token",…))`.

### Audio — Music & Guitar
- [Music players](https://github.com/Haven-hvn/docs/blob/main/architecture/02-haven-dapp.md) - Generic `audio/*` (`mp3`/`flac`/`wav`) CIDs: Haven Web player, `vlc`/`mpv` wrappers and mobile Media3 player.
- [Guitar files](https://github.com/Haven-hvn/docs/blob/main/architecture/03-haven-cli.md) - `psarc` (Rocksmith) / `psarc guitar files`, `gp5`/`gp` tabs and stems: open-source `psarc` extractor, tab viewer/renderer, practice player and stem splitter — all parse same CID.

### Documents — Ebooks
- [Ebook readers](https://github.com/Haven-hvn/docs/blob/main/architecture/04-haven-mobile.md) - `epub`/`pdf` CIDs per DataDAO zone: `epub.js`/`pdf.js` viewers, Readium and `haven-cli` ebook converter — same `encrypted_cid` and epoch.

## Concepts
Haven L7 is `alt.binaries for DataDAOs` — a private-tracker replacement that is token-gated, sealed and permanently pinned. Files are stored as CIDs: entity headers are ephemeral (`btl`/`EXPIRE`), bodies are durable (Filecoin `PDPVerifier`).

## Contributing
PRs welcome! Each DataDAO may ship its own GUI around the same file protocol. See `awesome.md` and `interfaces/README.md`. Please follow [awesome guidelines](https://github.com/sindresorhus/awesome/blob/main/pull_request_template.md).

## Planet Visualization
Interactive orbit view of composable permissionless networks: [planet/index.html](planet/index.html) — Haven L7 at center, Arkiv L3, ICP VetKD, EVM, Filecoin as orbits, many UIs around one file CID. No private backend — only CIDs + eth_call + ecrecover.
