# Little Moments shared reminder library

Public reminder collections for the Little Moments iPhone and iPad app. The app downloads `catalog.json`, shows available collections, and imports a selected JSON file into an editable local draft. Users do not need a GitHub account. This repository contains only public library content, never users' saved reminders or the app source.

## Publish a collection

1. Prepare a UTF-8 JSON array with 1–200 objects. Each needs `title`; `description` and `details` are optional strings. Keep each file under 1 MB.
2. Add the file under `collections/` using a new versioned filename, for example `daily-habits-v1.json`. Use only letters, digits, hyphens, and underscores in the filename.
3. Add an entry to `catalog.json` with a stable unique `id`, `title`, `summary`, accurate `reminderCount`, and relative `file` path. Keep `schemaVersion` at 1. An empty collections array is supported.
4. Commit and push both the file and catalog to `main`. The app reads the catalog when users open or refresh the cloud library. GitHub caching can delay visibility for a few minutes.

When updating content, add a new filename and point the catalog entry at it. Keep old versioned files so users who loaded an earlier catalog can still download them. Remove a catalog entry to unlist a collection. Changes never overwrite users' previously imported copies.

Example reminder file:

```json
[
  {
    "title": "Take a break",
    "description": "Stand up and stretch.",
    "details": "Use a short break between tasks to move around."
  }
]
```

The initial English collections come from the app's existing prepared import sets. IPA and respellings are approximate learning aids.
