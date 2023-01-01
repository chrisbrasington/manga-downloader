# manga-downloader-sync

Downloads images (manga) from the web into cbz files, converts to pdf,  and syncs between local cache and a device folder. Cache ensures files will not redownload.

## site support

- [danke.moe](https://danke.moe/) (best)
- [mangadex](https://mangadex.org/)
- generic rss feeds maybe ?

## device support

tested with `kobo libra 2` and will work with any device that supports cbz (zip) files

<img src=".img/sample.png" style="width:100%">

## features
`sources.txt` can support a flag to combine all chapters into a single file for thos manga that like to be a page or two a chapter

> url, True

## run

Modify `sources.txt` run with python 3

> python program.py  

## sample sources

> Note: `mangadex` is looking for the GUID out of the url

```
https://danke.moe/read/manga/the-tsuntsuntsuntsuntsuntsuntsuntsuntsuntsuntsundere-girl/, True
https://danke.moe/read/manga/OL-cafe-crush/
https://mangadex.org/title/e5148679-29de-4fff-b1a1-c77c44c41d5a/crest-of-the-stars
```

## language

Hardcoded to `en` atm

## output
```
✓ kobo detected
The Tsuntsuntsuntsuntsuntsuntsuntsuntsuntsuntsundere Girl Getting Less and Less Tsun Day by Day - danke.moe
  ✓ up-to-date: Chapter: 83
  Syncing to device...
    ✓ The Tsuntsuntsuntsuntsuntsuntsuntsuntsuntsuntsundere Girl Getting Less and Less Tsun Day by Day.cbz (combined)
The Overworked Office Lady's Café Crush - danke.moe
OL-cafe-crush-3.cbz: 100%|█████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████| 15.1M/15.1M [00:00<00:00, 458MB/s]
  ✓ OL-cafe-crush-3.cbz
  Syncing to device...
    ✓ OL-cafe-crush-3.cbz
    ✓ OL-cafe-crush-2.cbz
    ✓ OL-cafe-crush-1.cbz
Crest of the Stars - mangadex
  ✓ Crest of the Stars 5
  [...]
```