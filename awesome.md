# Awesome Haven — Curated UIs around Files

Directory of interfaces built around Haven L7 file CIDs. PRs welcome.

## Core Protocol
- [Haven docs](https://github.com/Haven-hvn/docs) — architecture/WEB3_PARADIGM, ENTITY_SHAPE
- [haven-aol](https://github.com/Haven-hvn/haven-aol) — Always Online, VetKD gating for DAOs/DataDAOs/agent swarms
- [arkiv-op-reth](https://github.com/Haven-hvn/docs) — Arkiv OP L3 reth `0x44…0044` (local)

## Clients (reference)
- [haven-dapp](https://github.com/Haven-hvn/haven-dapp) — Next.js 15, `arkiv_query`, decrypt, playback
- [haven-cli](https://github.com/Haven-hvn/haven-cli) — Python 3.11+, `arkiv_sync.py`, encryption, archival
- [haven-mobile](https://github.com/Haven-hvn/haven-mobile) — Kotlin Compose/Media3/Room, foc-cache
- [foc-local-first-android](https://github.com/Haven-hvn/foc-local-first-android) — 3 paths (SP /piece, FilBeam CDN, IPFS) hedged race, LRU/TTL

## Clients (experimental — incubator)
- [haven-clients-experimental](https://github.com/Haven-hvn/haven-clients-experimental) — SLOP testbed for `audio/*`, `image/*`, `pdf/epub`, `csv/parquet`, `safetensors`, `gltf` etc. (`clients/<name>/` per client). Merged PRs count under `haven`; graduates promote to standalone `Haven-hvn/<client>` repos/projects

## Interfaces around Files
- *Add your UI here* — gallery, player, CLI, agent swarm, bulletin, tracker replacement — all read `CID` via same `arkiv_query` + `gate_token`

## Concepts
- [Haven](https://github.com/Haven-hvn/docs) — `headers + CID + btl` gossip, body on Filecoin, timeless and p2p — `alt.binaries for DataDAOs`.

## Example File Types → Multiple Open-Source Clients
- **psarc (guitar)** — `psarc` extractor, Rocksmith custom song loader, tab renderer — all open-source clients around one `psarc` CID
- **Music** — `vlc`, `mpv`, Haven Web player, mobile Media3 player — same `audio/*` CID
- **Ebooks** — `epub.js` reader, `pdf.js` viewer, `haven-cli` `ebook` converter — same `application/epub+zip` CID per DataDAO
