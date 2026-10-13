# RoboAffect

Multimodal dataset of first-person (ego) movie-watching responses and aligned movie frames, organized for release.

## Layout

```text
github_release/
├── ego/
│   ├── video/{genre}/{condition}/{trailer_id}.mp4   # Hugging Face only (not in this repo)
│   ├── frames/{genre}/{condition}/{trailer_id}/00000000.jpg
│   ├── audio/{genre}/{condition}/{trailer_id}.wav
│   └── narrative/{trailer_id}.json
├── raw/
│   ├── frames/{genre}/{trailer_id}/00000000.jpg
│   ├── audio/{genre}/{trailer_id}.wav               # not yet included
│   └── narrative/{trailer_id}.json
├── annotations/
│   ├── confidence/{genre}/{trailer_id}/{A..E}.json  # placeholder; merge local annotations
│   └── reasoning/{genre}/{trailer_id}/{A..E}.json
└── metadata/
    └── trailers.csv
```

## Naming

| Field | Rule | Example |
| --- | --- | --- |
| `genre` | one of 8 emotion genres | `Action_Tense` |
| `condition` | `{height}_{distance}_{angle}` | `1.3m_near_right` |
| `trailer_id` | `{id}_{title}_{year}` (spaces kept) | `0001_1917_2019` |
| frames | 8-digit, 1 FPS from 0 | `00000000.jpg` |

Genres: `Action_Tense`, `Comedy_Cheerful`, `Depressive_Dark`, `Inspirational_Hopeful`, `Mystery_Reflective`, `Romantic_Warm`, `Thriller_Horror`, `Tragic_Sad`.

Conditions: `0.8m` / `1.3m` × `near` / `middle` / `far` × `left` / `center` / `right` (18 total).

## What is in this GitHub repo

Lightweight release files only (GitHub rejects a ~5 GB media push):

| Asset | In GitHub | Notes |
| --- | --- | --- |
| `ego/narrative` | yes | 215 JSON files |
| `raw/narrative` | yes | same content as ego |
| `metadata/trailers.csv` | yes | inventory of 224 trailers |
| `annotations/` | placeholders | merge local confidence/reasoning |
| `ego/frames`, `ego/audio`, `raw/frames` | on disk / HF | prepared locally; not tracked here |
| `ego/video` | Hugging Face only | ignored by git |
| `raw/audio` | missing | |

Nine trailers have frames but no ego audio / narrative yet: `0028`, `0030`, `0042`, `0064`, `0097`, `0141`, `0147`, `0165`, `0225`.

## Genre id ranges used for this packaging

| IDs | Genre |
| --- | --- |
| 0001–0030 | Action_Tense |
| 0031–0054 | Comedy_Cheerful |
| 0055–0082 | Depressive_Dark |
| 0083–0113 | Inspirational_Hopeful |
| 0114–0143 | Mystery_Reflective |
| 0144–0176 | Romantic_Warm |
| 0177–0202 | Thriller_Horror |
| 0203–0229 | Tragic_Sad |

## Citation

TBD.
