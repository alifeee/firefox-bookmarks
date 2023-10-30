# Firefox bookmarks

This is an exporter for Firefox bookmarks. It is designed so that I can easily share (some of) my bookmarks on my website.

## To use

1. Go to `about:support` (`Alt, H, T`)
1. Open `Profile Folder`
1. Copy `places.sqlite` to this repository

Run [`read_bookmarks.py`](./read_bookmarks.py) with the bookmark folders you would like exported. For me, that's

```bash
py .\read_bookmarks.py -f "personal websites" "Articles (random)"
```

You now have `bookmarks.json` which can be used wherever it needs to be used.

For an example, see [example.html](./example.html).
