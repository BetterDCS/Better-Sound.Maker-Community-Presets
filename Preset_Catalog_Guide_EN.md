# Preset Catalog Guide (BSM)

Better Sound Maker (BSM) presets are shared through the **BetterCommunity preset
catalog**. A preset is a single JSON file describing a sound configuration and the
asset files it references. This guide covers the format and how to publish one.

> [!NOTE]
> A preset carries all of its metadata *inside* the JSON — there is no separate
> catalog entry to fill in. Upload the `.json` and the catalog reads it.

---

## 1. Preset JSON format

```json
{
  "name": "Afterburner Boom",
  "version": "1.0.0",
  "color": "#f97316",
  "UpdateNumber": 3,
  "date": "2026-07-01",
  "assetPaths": [
    "sounds/ab_ignite.wav",
    "sounds/ab_loop.wav",
    "sounds/ab_cut.wav"
  ]
}
```

| Field | Type | Required | Purpose |
|---|---|---|---|
| `name` | string | **Yes** | Display name |
| `version` | string | **Yes** | SemVer version string |
| `assetPaths` | string[] | **Yes** | Relative paths of the sound assets the preset uses |
| `color` | string | No | Accent colour (`#rrggbb`) for the card |
| `UpdateNumber` | number | No | Increment on each update |
| `date` | string | No | `YYYY-MM-DD` last-updated date |

The server validates this shape on submit — an invalid preset is rejected with the
offending fields.

---

## 2. Publishing to the catalog

1. Open **Dashboard → Submit content**.
2. Project = **BSM**, Type = **Preset** (BSM only offers presets).
3. Pick your preset `.json` — the editor auto-fills the name/version from the file.
4. Submit. A moderator reviews it before it goes live.

> [!TIP]
> Use **Generate template** in the submit modal to start from a valid skeleton.

---

## 3. Downloading presets

On the **Catalog** (filtered to BSM) you can:

- **Download** a single preset from its card or detail page.
- **Select several** with the checkboxes and **Download selected** to grab them all
  at once.
- **Sort/filter** by *Most popular (all-time)*, *Popular this month*, *Newest*, or
  *Most viewed*.

Every download is counted, so uploaders can see how many times their presets were
downloaded from the item's stats.

---

## 4. Updating a preset

Bump `version` (and `UpdateNumber`), re-upload from **My items → propose update**.
The change is re-reviewed before replacing the live version.
