# Interfaces — Many UIs around the Same File CID

Haven L7 is `headers + CID` only in Arkiv. Every interface below reads the same `ipfs_cid`/`piece_cid` via Filecoin (SP /piece, FilBeam CDN, IPFS) and decrypts via `haven-aol` VetKD if `is_encrypted=1`. Different DataDAOs ship different GUIs around the same file protocol.

## Audio
- **Music players** — generic players for any `content_mime_type: audio/*` (`mp3/flac/wav` CID) — e.g. Haven player, Web player, CLI `mpv` wrapper
- **Guitar files** — `psarc` / `psarc guitar files` (Rocksmith), `gp5`/`gp` tabs, stems — open-source clients parse the same CID: tab viewer, practice player, stem splitter

## Documents
- **Ebook readers** — `epub/pdf` CIDs gated by DataDAO — Readium, custom reader, CLI `pandoc` pipeline — same `encrypted_cid` + VetKD epoch

## Gate per DataDAO
Each DataDAO zone (`gate_token/gate_chain/gate_threshold`) gets its own GUI but same wire: `arkiv_query(eq("gate_token",…)) → CID → IPFS cat → VetKD decrypt`.

Add yours via PR to `../awesome.md`.
