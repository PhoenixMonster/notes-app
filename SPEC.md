# Notes App

A personal notes app to replace ColorNote. Clean, uncluttered, works on phone first, desktop later.

## Principles

- Local-first: notes live on the device, no backend in v1
- Installable PWA (phone home screen + desktop browser)
- Notes stored as plain markdown text
- Data model is sync-ready: UUID, createdAt, updatedAt, archivedAt, deletedAt per note
- Soft delete only (deletedAt), so deletions can sync later

## Stack

Vite + React + TypeScript

## Plan

1. Core: create, edit, list, archive, delete from archive. Then: deploy to a static host, add vite-plugin-pwa, make installable on phone. Request persistent storage on startup (navigator.storage.persist()).
2. Comfort: search, pinning, other must-haves (TBD)
3. Safety: export / import
4. Sync: backend, login, desktop editing

- Server-based sync behind a pull()/push() interface, so the backend stays swappable
- Backend TBD (PocketBase or Supabase)
- Last-write-wins on updatedAt, deletedAt tombstones
- Dexie stays as the local working copy on every device

## Not now

Images, rich-text editor, multi-user, anything not listed above.
