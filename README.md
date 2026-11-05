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

## Little Chunks modules 02–08

Originally imported from [Little Chunks](https://little-chunks-felix-1105.tomchanatuk.chatgpt.site) on 5 November 2026. Each module contains 20 reminders (140 total). The current library editions have been independently revised for practical everyday conversation; they are no longer exact copies of the website. Module 01 is reserved on the source site and is not included. These seven modules do not include IPA or pronunciation guides.

- 02 · Opinions & feelings
- 03 · Storytelling
- 04 · Socialising & relationships
- 05 · Explaining & reasoning
- 06 · Work & university
- 07 · Everyday British English
- 08 · Fluency & conversation flow

## Everyday conversation revision — 5 November 2026

All nine catalog collections (192 cards) have revised meanings, examples, and usage notes. The seven conversation modules favour reusable spoken phrases over formal argument, workplace clichés, and elaborate idioms. The British English module now covers ordinary greetings, shopping, food, and daily arrangements. This is an editorial selection for usefulness, not a measured frequency ranking.

The two original food and learning packs retain their topics. Their explanations now work without the original cooking video. The pronunciation pack retains its existing British IPA and approximate respellings, with corrected meaning/context where needed. Its short label “Call her?” is distinguished from the longer example question.

Every card has a short `Example:` followed by a separate `Usage:` note. This lets the companion widget extract the example while keeping fuller explanations in the app. Collection IDs remain stable and previously published files are retained for cached catalogs.

To get these editions in the app, refresh **Import reminders → Browse cloud library**, then import the collection as a new local copy. Previously imported reminders and quiz history are not overwritten. Importing into an existing collection appends cards; it does not replace or merge the older edition.
