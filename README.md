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

- Texts (transliterations + metadata): the
  [electronic Babylonian Library (eBL)](https://www.ebl.lmu.de/), Jiménez et al.,
  LMU Munich, **CC BY-NC-SA 4.0**; and [ORACC](https://oracc.org/), **CC BY-SA 3.0**.
  No eBL tablet images are included. Each text deep-links to its eBL edition page.
- Translations: fine-tuned LLMs (Gemma / Mistral), following the approach of
  Gutherz et al. (2023), *Translating Akkadian to English with neural machine
  translation*, PNAS Nexus.

## License

Text data is reused with attribution for **non-commercial** use under the source
terms (eBL CC BY-NC-SA 4.0, ORACC CC BY-SA 3.0). Because it incorporates eBL's
CC BY-NC-SA 4.0 material, the combined dataset (`reader.sqlite`) is shared under
[**CC BY-NC-SA 4.0**](https://creativecommons.org/licenses/by-nc-sa/4.0/) —
non-commercial, share-alike, attribution required. The site code is MIT; the
vendored `sql.js` is MIT. See [LICENSE](LICENSE) for the full statement and the
per-edition citation format.

Part of **The Assyriologist** — an Akkadian→English translation & analysis project
(a three-part Wolfram Community series).
