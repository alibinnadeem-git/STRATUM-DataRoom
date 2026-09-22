# STRATUM DataRoom

Canonical repository for the STRATUM DataRoom platform.

## Current baseline

**Latest known release:** R6.8 — Full Google Drive Mirror  
**Build ID:** `STRATUM_DATAROOM_R6_8_FULL_DRIVE_MIRROR_2026-09-14`

### R6.8 behavior

- Configured Google Drive root mirrors into the managed STRATUM DataRoom structure.
- Each top-level Drive folder becomes a Data Room when not already mapped.
- Nested Drive folders become managed folders/subfolders.
- Drive files become managed DataRoom documents.
- Files directly in the configured Drive root are placed in a dedicated **Drive Root Files** Data Room.
- Existing mappings are preserved to prevent duplication.
- Post-deployment flow is intended to run a full Google Drive sync automatically.

## Release verification status

The R6.8 implementation is the latest identified source baseline. Production verification remains required for the complete full-mirror flow, including:

- mapping preservation
- nested folders
- root-level files
- post-deployment synchronization
- RBAC / permissions
- CRUD and archive/restore flows
- UI workflows
- JARVIS / Spatial Verified / AI Costing integration boundaries

## Source integrity

Do not replace the R6.8 source with a reconstruction or older R6.x/R5 archive. The canonical source archive previously produced was:

`stratum-dataroom-r6-8-full-drive-mirror-20260914.zip`

Secrets, credentials, service-account keys, database connection strings and local `.env` files must never be committed.

## Production

Historical production target:

`https://stratum-dataroom.vercel.app`
