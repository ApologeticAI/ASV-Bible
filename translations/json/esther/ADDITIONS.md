### Esther — Additions A–F (Chapters 11–16)

This dataset keeps the main Hebrew/Protestant Esther text as **chapters 1–10**, and stores the Greek “Additions to Esther” as **additional chapter files 11–16**:

- `translations/json/esther/chapter-11.json` — **Addition A** (Prologue / Mordecai’s Dream)
- `translations/json/esther/chapter-12.json` — **Addition B** (Haman’s Edict)
- `translations/json/esther/chapter-13.json` — **Addition C** (Prayers of Mordecai and Esther)
- `translations/json/esther/chapter-14.json` — **Addition D** (Esther Approaches the King)
- `translations/json/esther/chapter-15.json` — **Addition E** (Decree for the Jews)
- `translations/json/esther/chapter-16.json` — **Addition F** (Interpretation of Dream / Purim conclusion)

Each addition chapter includes a `heading` field on its first verse (and where helpful inside the chapter) for UI section labeling.

### Recommended interleaving order (to match the story flow)

If your app wants to display the additions in the traditional narrative positions, insert them like this:

- **Addition A (Esth 11)**: before **Esth 1:1**
- **Addition B (Esth 12)**: after **Esth 3:15** (after the decree is issued)
- **Addition C (Esth 13)**: after **Esth 4:17** (after the call to fasting and resolve)
- **Addition D (Esth 14)**: between **Esth 5:1** and **Esth 5:2** (it expands that moment)
  - If you can’t insert between verses, place it immediately after **Esth 5:1**
- **Addition E (Esth 15)**: after **Esth 8:17** (after the reversal and public joy)
- **Addition F (Esth 16)**: after **Esth 10:3** (as the conclusion)
  - Note: **Esth 16:11** is a colophon-style transmission note about the Letter of Purim.

### If you don’t need interleaving

If you simply load chapters in numeric order, reading **Esth 1–16** will place the additions after the main narrative. To preserve the intended story placement, use the interleaving map above.


