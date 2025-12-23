## Apostolic Inspired Version (AIV) — JSON Bible

A chapter-by-chapter JSON dataset of the **Apostolic Inspired Version (AIV)** Bible translation, including:

- **Verse text**
- **Cross-reference links** (stored as HTML anchor tags)
- **Commentary** (short notes per verse)

## Directory structure

Books are stored in `json/` and each chapter is a separate file:

- **Book folder**: `json/<book-slug>/`
- **Chapter file**: `chapter-<n>.json` (1-based)

Example paths:

- `json/genesis/chapter-1.json`
- `json/1-corinthians/chapter-13.json`

## JSON schema

Each `chapter-<n>.json` looks like this:

- **book**: string (human-readable book name, e.g. `"Genesis"`)
- **bookAbbreviation**: string (e.g. `"Gen"`, `"1Cor"`)
- **chapter**: number
- **verses**: array of verse objects
- **translatedAt**: string (ISO-8601 timestamp)

Each verse object in `verses[]` includes:

- **pk**: number (unique identifier)
- **translation**: string (currently `"AIV"`)
- **book**: number (internal numeric id; not guaranteed to be unique across every folder—use the top-level `book`/`bookAbbreviation` or the folder name for identification)
- **chapter**: number
- **verse**: number
- **text**: string
- **links**: string (HTML; may be empty)
- **comment**: string (may be empty; may contain HTML)

## Usage examples

### Node.js (ESM)

```js
import { readFile } from "node:fs/promises";

const chapter = JSON.parse(
  await readFile("json/genesis/chapter-1.json", "utf-8"),
);

// Print Genesis 1:1
const v1 = chapter.verses.find((v) => v.verse === 1);
console.log(v1.text);
```

### Python

```python
import json
from pathlib import Path

chapter = json.loads(Path("json/genesis/chapter-1.json").read_text(encoding="utf-8"))

# Print Genesis 1:1
print(chapter["verses"][0]["text"])
```

## Notes

- **`links` is HTML**: if you render it in an app or on the web, treat it as untrusted HTML unless you control the full pipeline (sanitize if needed).
- **Empty fields**: `links` and `comment` can be `""` for some verses.