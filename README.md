# Museum Tour Journal

A responsive, mobile-first prototype based on `museum-tour-app-prd.md`.

## Run locally

This version has no build step or dependency install:

```bash
python -m http.server 4173
```

Then open <http://127.0.0.1:4173>.

## Included in the prototype

- Demo email, Google, and Apple sign-in entry points
- Exhibition dashboard with search, collections, storage status, and recent visits
- Create/edit exhibition modal with required fields
- Exhibition reference search with save/open actions and gallery-wall layout
- Working drag and resize wall mode with persisted positions
- Multi-photo artwork upload and camera capture entry points using browser file inputs
- Drag-and-resize crop editor for artwork images and caption images before OCR
- Artwork detail view with add/edit notes, tags, metadata, and caption/OCR review
- Delete confirmations for artworks and exhibitions
- Collection creation, assignment, filtering, and counts
- Collection manager with delete actions and a clear return to All exhibitions
- Most-recent / oldest exhibition sorting
- Local persistence for exhibitions, artworks, notes, links, collections, and layout via `localStorage`
- Responsive mobile layout

This build now has a functional local service layer. Real authentication, cloud photo storage, sync conflict resolution, and a production reference-search API still need a backend and provider credentials for a production release. Caption scanning uses Tesseract.js when its CDN and language data are available, with an editable fallback when offline.
