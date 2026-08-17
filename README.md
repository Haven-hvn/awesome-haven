# Awesome Haven [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> Curated directory for **Haven — L7 sovereign media protocol** (BTP/GTP — Bulletin/Gossip Transfer Protocol). Files as CIDs: Arkiv OP L3 (`0x44…0044` ephemeral entities, `btl`/`regex` via `roaring64/ART`) + ICP VetKD (`haven-aol` `dciac-…qlzuq`, `gate_token/gate_chain/gate_threshold` per `cid/epoch`) + Filecoin Onchain Cloud (IPFS `CID` only in Arkiv). Many UIs around the same file pointer — no private backend (`Datastores:0`).

## Contents
- [Protocol](#protocol)
- [Clients](#clients)
- [Interfaces — Many UIs Around Files](#interfaces--many-uis-around-files)
  - [Audio — Music & Guitar](#audio--music--guitar)
  - [Documents — Ebooks](#documents--ebooks)
- [Concepts](#concepts)
- [Contributing](#contributing)

## Protocol
- [Haven docs](https://github.com/Haven-hvn/docs) - Living architecture, `WEB3_PARADIGM`, `ENTITY_SHAPE` (`Ident32`/`Mime128`/`btl` at `0x44…0044`), `MEDIA_CONTENT_SPEC` (`CID`-only body)
- [haven-aol](https://github.com/Haven-hvn/haven-aol) - Always Online, ICP-native VetKD gating for DAOs/DataDAOs/agent swarms
- [arkiv-op-reth](https://github.com/Haven-hvn/docs) - Arkiv OP L3 reth reference (`just node-dev` 1337 or `braga.hoodi.arkiv.network/rpc` or both)

## Clients
Reference thin clients obeying the same file-CID rule set:

- [haven-dapp](https://github.com/Haven-hvn/haven-dapp) - TypeScript/Next.js 15 Web3 frontend (`arkiv_query`, decrypt, playback)
- [haven-cli](https://github.com/Haven-hvn/haven-cli) - Python 3.11+ media pipeline (`arkiv_sync.py`), encryption, archival — *Reclaiming the Internet for the User.*
- [haven-mobile](https://github.com/Haven-hvn/haven-mobile) - Kotlin Compose/Media3/Room, offline-first with `foc-cache`
- [foc-local-first-android](https://github.com/Haven-hvn/foc-local-first-android) - Kotlin/Android 3-path retrieval (direct SP `/piece`, FilBeam CDN, IPFS) hedged race, LRU/TTL

## Interfaces — Many UIs Around Files
Same `ipfs_cid`/`piece_cid` via Filecoin, `haven-aol` VetKD if `is_encrypted=1`, discovered via `arkiv_query(eq("gate_token",…))`.

### Audio — Music & Guitar
- Music players - Generic `audio/*` (`mp3`/`flac`/`wav`) CIDs: Haven Web player, `vlc`/`mpv` wrappers, mobile Media3 player
- Guitar files - `psarc` (Rocksmith) / `psarc guitar files`, `gp5`/`gp` tabs, stems: open-source `psarc` extractor, tab viewer/renderer, practice player, stem splitter — all parse same CID

### Documents — Ebooks
- Ebook readers - `epub`/`pdf` CIDs per DataDAO zone: `epub.js`/`pdf.js` viewers, Readium, `haven-cli` ebook converter — same `encrypted_cid` + epoch

## Concepts
- `alt.binaries for DataDAOs` - Private-tracker replacement, token-gated, sealed, permanent pin
- `GTP/BTP — Gossip/Bulletin Transfer Protocol` - `headers + CID + btl` gossip, body on Filecoin
- `Distributed Bulletin Transfer Protocol (DBTP)` - Timeless + p2p
- `Files as CIDs` - Entity headers ephemeral (`btl`/`EXPIRE`), body durable (Filecoin `PDPVerifier`)

## Contributing
PRs welcome! Each DataDAO may ship its own GUI around the same file protocol. See `awesome.md` and `interfaces/README.md`. Please follow [awesome guidelines](https://github.com/sindresorhus/awesome/blob/main/pull_request_template.md).

## License
CC0 — see `LICENSE`.
