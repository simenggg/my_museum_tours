# Product Requirements Document: Museum Tour Journal

## 1. Product overview

Museum Tour Journal is a mobile-first app for recording museum visits. It helps users connect artwork photos, caption information, personal thoughts, research notes, and exhibition details in one private, searchable journal.

The first version will support iOS and Android. A web version may be developed later.

## 2. Target audience

- Museum enthusiasts who photograph many artworks
- Art students and art-history majors
- Artists and designers collecting inspiration
- Travelers documenting museum visits
- Users who want an organized cultural or visual journal

## 3. User problem

Museum photos often become mixed together in a phone gallery, while captions, personal interpretations, and research links are stored separately. Users need a visually appealing way to organize each visit and preserve the ideas connected to individual artworks.

## 4. Product goals

1. Make it easy to create a record of each exhibition visit.
2. Let users quickly capture or upload many artwork photos.
3. Connect multiple photos, caption text, structured artwork information, notes, and links to one artwork.
4. Provide an aesthetic gallery-wall presentation of each exhibition.
5. Support offline recording and cloud synchronization.

## 5. MVP scope

### Included

- Required account with email/password, Google, and Apple sign-in
- Cloud backup and synchronization
- 5 GB cloud photo storage per user
- Private records only; no sharing
- iOS and Android support
- Create, edit, and delete exhibitions
- Create, edit, delete, and merge artworks
- Take photos in the app or select existing phone photos
- Upload multiple photos at once
- Automatic exhibition reference-link search
- Caption-photo OCR with automatic language detection for English, Chinese, and Japanese
- Review and editing of OCR results
- Optional artwork metadata
- Free-text notes with tags
- Offline photo and note creation, followed by synchronization
- Search and folder/collection organization for exhibitions
- PDF or other export functionality is excluded from the MVP

## 6. Core information architecture

```text
User
└── Folders / Collections
    └── Exhibitions
        ├── Exhibition details and selected reference links
        └── Artworks
            ├── Primary photo
            ├── Additional photos
            ├── Caption photos and extracted text
            ├── Optional artwork metadata
            └── Tagged free-text notes
```

## 7. Main user flows

### 7.1 Create an exhibition

1. User taps “Add exhibition.”
2. User enters exhibition name, museum name, and visit date.
3. User may add an optional description and cover image.
4. The app automatically searches online for relevant references.
5. The app displays reference links.
6. User opens each link, decides whether it is relevant, and chooses which links to save.

### 7.2 Add artworks

1. User opens an exhibition and taps “Add artworks.”
2. User takes photos in the app or selects many photos from the phone.
3. Each photo initially becomes a separate artwork.
4. The first photo for each artwork is its primary photo.
5. User can later change the primary photo.
6. User can merge artworks when multiple photo records represent one artwork.

### 7.3 Add caption information

1. User opens an artwork.
2. User uploads or takes a caption photo.
3. The app detects English, Chinese, or Japanese automatically.
4. OCR extracts the caption text.
5. User reviews and edits the extracted text.
6. User saves the corrected caption.

### 7.4 Add artwork notes

1. User opens an artwork.
2. User enters a free-text note.
3. User assigns one or more tags, including “Research,” “My thoughts,” or “Links.”
4. User saves, edits, or deletes the note.

### 7.5 Browse an exhibition

1. Main page shows all exhibitions, ordered by most recent visit first.
2. User searches for a particular exhibition or browses folders/collections.
3. User opens an exhibition.
4. Artworks appear in an automatically generated wall-style layout with varied image sizes and positions.
5. User can drag, reposition, and resize artworks.
6. User taps an artwork to view its notes, captions, metadata, and additional photos.

## 8. Functional requirements

### Authentication and data

- Users must authenticate before using the app.
- The system must support email/password, Google, and Apple sign-in.
- Records must be private to the account.
- Data must sync across the user’s supported devices when online.
- The app must show storage usage and prevent uploads after the 5 GB limit is reached.

### Exhibition management

- Exhibition name, museum name, and visit date are compulsory.
- Description and cover image are optional.
- Users can create, view, edit, and delete exhibitions.
- Users can search exhibitions by relevant text.
- Users can create folders or collections and organize exhibitions within them.
- Users can save or remove selected online reference links.

### Artwork management

- Users can upload multiple artwork photos in one action.
- Users can capture photos using the device camera.
- Each uploaded photo initially creates one artwork record.
- Users can add additional photos to an artwork.
- Users can select a different primary photo.
- Users can merge two or more artwork records.
- Users can edit and delete artwork records.
- Each artwork can optionally store title, artist, year, medium, and museum location.

### Gallery-wall layout

- The system must generate an initial non-uniform wall-style layout.
- The overview must display one primary photo per artwork.
- Users must be able to drag and reposition artwork cards.
- Users must be able to resize artwork cards.
- Layout changes must persist after synchronization.

### OCR and captions

- Users can upload or capture caption photos.
- OCR must automatically detect English, Chinese, and Japanese.
- Extracted text must be editable before saving.
- The original caption image should remain attached to the artwork.

### Notes

- Users can create, edit, and delete free-text notes for an artwork.
- Notes can have tags.
- The initial tag set must include “Research,” “My thoughts,” and “Links.”

### Offline mode

- Users can create exhibitions, add photos, and add notes without an internet connection.
- Offline changes must be queued locally.
- Queued changes must synchronize when connectivity returns.
- The app must communicate sync status and any sync conflicts clearly.

## 9. Non-functional requirements

- Responsive mobile interface for iOS and Android.
- Secure account authentication and private data access.
- Reliable upload retry behavior for unstable museum connectivity.
- Image compression or optimization should be considered to reduce storage and upload time while preserving useful artwork detail.
- The interface should prioritize visual appeal, legibility, and quick capture during a museum visit.

## 10. Out of scope for MVP

- Web application
- Public profiles or sharing links
- Export to PDF or other formats
- Automatic importing of full exhibition information
- Automatic summarization or interpretation of references
- Social features, comments, or collaboration

## 11. Success metrics

- Percentage of new users who create their first exhibition
- Percentage of exhibitions with at least one artwork
- Number of artworks recorded per exhibition
- OCR correction completion rate
- Successful offline-to-online synchronization rate
- Seven-day and thirty-day user retention
- Percentage of users who return to browse a previous exhibition

## 12. Open product decisions

- Exact online search providers and supported reference sources
- Maximum individual image size and supported image formats
- Whether a folder can contain other folders
- Conflict-resolution behavior when the same record is edited on multiple devices
- Whether users can undo deletion or whether deletion is permanent
- Accessibility requirements, including font scaling and screen-reader support
