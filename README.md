# STRATUM DataRoom

Reproducible source repository for STRATUM DataRoom.

## Build
**R7.0 reconstructed baseline — 2026-09-22**

This is a new clean build reconstructed from the latest documented R6.8 Full Drive Mirror requirements. It is **not represented as byte-for-byte recovery of the unavailable R6.8 source archive**.

## Implemented baseline
- Next.js application shell
- STRATUM DataRoom UI
- health API
- Google Drive service-account client
- Drive-root discovery/sync endpoint
- Neon/Postgres schema for rooms, folders, documents, mappings and audit events
- environment template
- reproducible npm build configuration
- no credentials committed

## R6.8 mirror contract
- top-level Drive folders become Data Rooms
- nested folders become managed folders/subfolders
- Drive files become managed documents
- root files belong in a dedicated Drive Root Files Data Room
- existing mappings are preserved
- synchronization must be idempotent

## Run
1. `npm install`
2. Copy `.env.example` to `.env.local` and configure secrets.
3. Apply `db/schema.sql` to the target Postgres/Neon database.
4. `npm run dev`

## APIs
- `GET /api/health`
- `POST /api/drive/sync`

## Security
Never commit service-account keys, database URLs, tokens or local environment files.

## Next release gates
Full persistence materialization, authentication/RBAC, CRUD/archive/restore, recursive Drive traversal, Admin Control Panel, JARVIS context, UAT and production deployment must be verified before calling this feature-equivalent to the historical R6.8 deployment.
