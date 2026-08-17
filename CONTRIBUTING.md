# Contributing

Add an interface that reads the same Haven file CID:

1. Fork, branch.
2. Add entry to `README.md` under correct category (alphabetical) with `description — link`.
3. Add to `awesome.md` if curated.
4. Interface must: discover via `arkiv_query` (`gate_token`), resolve `CID` via IPFS/Filecoin (SP/piece, FilBeam, IPFS), decrypt via `haven-aol` VetKD if `is_encrypted=1`.
5. Open PR.
