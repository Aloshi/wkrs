# Wanikani Radical Search

This is a static website that allows one to search for kanji using Wanikani radical names. Searching is done client-side in JavaScript. The interface uses the MaterializeCSS library (with some custom hackery to get chips + autocomplete working with fonts instead of images).

# Running

No setup necessary - just serve this directory through an HTTP server of your choice, e.g.:

```bash
git clone https://github.com/Aloshi/wkrs
cd wkrs
python -m SimpleHTTPServer
```

...and then open http://localhost:8000 in a web browser.

# How It Works

The radical and kanji data has been taken from the Wanikani API, lightly parsed to handle pagination, and saved as JSON in `data/`. At startup, the client fetches this data via ajax and fills in a MaterializeCSS autocomplete object with the radical data. Kanji searches are done by brute-force.

All radical/kanji data is copyright Wanikani (<3), pls no sue.

# TODO

* Set up a fallback font for Wanikani's "custom" radicals - https://github.com/iamale/WakaFont
* Move JavaScript from index.html to wkrs.jss
* Add a kanji -> vocab search as well
* Add support for personalization - e.g. show whether or not you've learned each kanji in the kanji list
* Manually add info for radicals that get superceded - e.g. the kanji 申 is taught as a combination of 十 and 口 at level 4, but it's later also taught as a radical (at level 11). Anything from levels 4-11 that looks like 申 will be classified as 十 + 口, but you'd type 申 into the search box once you learn it as a radical. I'll wait and see if this is actually a problem as I use the site.
