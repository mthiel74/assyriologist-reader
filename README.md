# The Assyriologist — Cuneiform Reader

A server-less, browser-based reader for **~19,700 machine-translated Akkadian &
Sumerian cuneiform texts**. Full-text search the English, filter by period, genre
and site, and read the cuneiform alongside its draft translation.

**Live:** https://mthiel74.github.io/assyriologist-reader/

> ⚠️ **These are unvetted machine translations** — research leads, *not* citable
> scholarly readings. They are produced by fine-tuned language models and frequently
> contain errors, especially on broken or fragmentary tablets. Always verify against
> the cuneiform and the primary editions before relying on any reading.

## How it works

Everything runs in your browser — there is **no server and nothing is tracked**:

- `reader.sqlite` — all texts in one SQLite file (~40 MB, ~12 MB gzipped).
- [`sql.js`](https://github.com/sql-js/sql.js) loads the whole database into memory
  once (the browser downloads it gzipped and decompresses it), then runs every
  search locally — no backend, no further network.
- Cuneiform is rendered with the
  [Noto Sans Cuneiform](https://fonts.google.com/noto/specimen/Noto+Sans+Cuneiform)
  webfont.

Searches are shareable via URL, e.g.
[`?q=eclipse&genre=Celestial`](https://mthiel74.github.io/assyriologist-reader/?q=eclipse&genre=Celestial).

## Data & credits

- Texts: the [electronic Babylonian Library (eBL)](https://www.ebl.lmu.de/) and
  [ORACC](https://oracc.museum.upenn.edu/).
- Translations: fine-tuned LLMs (Gemma / Mistral), following the approach of
  Gutherz et al. (2023), *Translating Akkadian to English with neural machine
  translation*, PNAS Nexus.

Part of **The Assyriologist** — an Akkadian→English translation & analysis project
(a three-part Wolfram Community series).
