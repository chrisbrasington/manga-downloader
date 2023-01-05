# manga-downloader-sync

Downloads images (manga) from the web into cbz files, converts to pdf,  and syncs between local cache and a device folder. Cache ensures files will not redownload.

<u>Only syncs newer chapters.</u> If older chapters are deleted from the device, only chapters after the latest chapter on device will be added. If no chapters exist on device, all chapters will be synced to device

## site support

- [mangadex](https://mangadex.org/)
- [danke.moe](https://danke.moe/)

## chapter number matching

Even if the feed changes, the chapter number is attempted to be extracted from the feed. This will not redownload cached chapter numbers even if the file name would be different.

### sources
`sources.txt` can support a flag to combine all chapters into a single file for those manga that like to be a page or two a chapter

> url, True

Or keeping as separate chapters..

> url

## device support

tested with `kobo libra 2` and will work with any device that supports cbz (zip) files

<img src=".img/sample.png" style="width:100%">

<img src=".img/sample2.jpg" style="width:100%">


## features

### summary of download/sync

Summary will display both download and synced information. If device is absent, will inform. If only sync happens, will inform.

### author

Author is added to PDF metadata

## run

>  pip install -r requirements.txt       

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

Hardcoded to `en` atm, and pretty much the first non-external source

## output
```
✓ kobo detected
Isekai Nihon - mangadex - Monsters, Action, Romance, Survival, Adventure, Post-Apocalyptic, Magic, Isekai, Gore, Drama, Fantasy
  ~~~~~
  As two worlds collide into one, a fateful counter between the "killer hero" and
  the "elf princess from another world" has led to a great adventure to defeat the
  even greater evil!
  ~~~~~
  ✓ cache: 1
  ✓ remote: 2
  ✓ downloading: 2 (en) None
100%|████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████████| 23/23 [00:13<00:00,  1.68it/s]
  ✓ done: 2
  converting to pdf... Isekai Nihon - 2.pdf
~~~~~~~~~~~~~~~~~~~~~
Content missing from device, synced to device
Isekai Nihon - 2.pdf
```