# Haven L7 Protocol — Files as CIDs

Spec: entity `headers + CID` only in Arkiv. See `Haven-hvn/docs` source of truth:
- `entities/ENTITY_SHAPE.md` — `Ident32` (bytes32 lowercase), `Mime128` (4×bytes32), `Attribute {name,valueType UINT/STRING/ENTITY_KEY, bytes32[4]}` + `Operation {CREATE..EXPIRE, btl: BlockNumber32}` at `0x44…0044`
- `entities/MEDIA_CONTENT_SPEC.md` — `title/duration/is_encrypted/encrypted_cid/piece_cid/content_mime_type` etc. For `news.*` / `alt.binaries`: `payload {ipfs_cid, content_mime_type, is_encrypted, gate_token gate_chain gate_threshold}`
- `architecture/05-arkiv-chain.md` — `arkiv_query` / `getEntityCount` / `getBlockTiming` via `roaring64 + ART`, no external indexer; `just node-dev` (1337) or `braga.hoodi.arkiv.network/rpc` or both
- `architecture/01-haven-aol.md` — `haven-aol` `dciac-uaaaa-aaaad-qlzuq-cai`, VetKD `accessol_v3` per `chain:token:threshold:epoch`, `balanceOf` gating (DataDAO-only today)

Principle: many UIs compete around the same file CID — dapp, CLI, mobile, foc-cache, agents — all thin clients obeying the same `Ident32` keys + `CID-only` body via IPFS.
