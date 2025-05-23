# Firefox bookmarks

This is an exporter for Firefox bookmarks. It is designed so that I can easily share (some of) my bookmarks on my website.

For my bookmarks, see <https://alifeee.co.uk/bookmarks/>

## To use

In Firefox,

1. Go to `about:support` (`Alt, H, T`)
1. Open `Profile Folder`
1. Copy `places.sqlite` to this repository

Run [`read_bookmarks.py`](./read_bookmarks.py) with the bookmark folders you would like exported. For me, that's

```bash
py read_bookmarks.py -f "TOP 10 personal websites/blogs" "other bookmarks lists" "webrings" "personal websites (with blog)" "personal websites (without blog)" "interesting websites" "Articles (random)" "Articles (programming)" "video playlists/channels" "wordles" "mobile games"

# or make .env with the profile folder location and use:
./run.sh
```

You now have `bookmarks.json` which can be used wherever it needs to be used.

For an example, see [example.html](./example.html).

## Build HTML

I want this page to be static, so I don't want to make a "frontend" (something that would need to download and parse the JSON). So, here I just make a static `index.html` file to push to my website.

```bash
pip install -r requirements.txt
py generate_html.py
```

It gets build to `index.html`.

## GitHub action

The action [`update.yml`](./.github/workflows/update.yml) in this repository updates two things when a new `bookmarks.json` file is pushed.

- [The gist `bookmarks.json`](https://gist.github.com/alifeee/5d84396d0404a879bb41329ec5afa9d3)
- The [`bookmarks.json` file](https://github.com/alifeee/alifeee.github.io/blob/main/bookmarks/bookmarks.json) on [my website](https://alifeee.co.uk/bookmarks/)
