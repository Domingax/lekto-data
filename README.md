# lekto-data

Dictionary data for [Lekto](https://github.com/Domingax/lekto), published outside
the application's releases (ADR-0047).

Each `dictionary-<YYYYMMDD>` release is one complete snapshot built from that
run's own bytes: every dictionary pack, difficulty table, per-artefact `NOTICE`
and `manifest-*.json`, and a `SHA256SUMS`.

The app follows one movable file:

```
https://github.com/Domingax/lekto-data/releases/latest/download/manifest.json
```

That manifest is the lock. Every entry names its own immutable dated URL and the
SHA-256 of the bytes behind it, so a download is verifiable and a reader never
mixes two snapshots. The manifest is published last, and only the three most
recent snapshots are kept.

The workflow that builds the snapshots is the application's reusable workflow,
[dictionary-data.yml](https://github.com/Domingax/lekto/blob/main/.github/workflows/dictionary-data.yml).
This repository holds only the scheduled caller,
[`.github/workflows/dictionary-data.yml`](.github/workflows/dictionary-data.yml).

## Licence

The dictionary data is derived from **Wiktionary** by **Wiktextract / Kaikki** and
is licensed **CC BY-SA 4.0** (and GFDL); the derived packs remain ShareAlike. The
difficulty bands derive from **wordfreq** by **Robyn Speer** (data CC BY-SA 4.0,
code Apache-2.0), which contains data from Google Books Ngram Viewer,
OpenSubtitles and the SUBTLEX word lists by Brysbaert et al. Every pack and table
carries its full `NOTICE-*` beside it, and the full licence text travels inside the
packs and tables.

Lekto is not affiliated with, nor endorsed by, the Wikimedia Foundation,
Wiktionary or wordfreq.
