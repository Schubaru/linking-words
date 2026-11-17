# Linking words

Sixteen words, four groups of four that mean the same thing. A new board every midnight.
Live at https://linking-words.vercel.app. A static site with no build step: Vercel serves the repo as-is.

## Where the game comes from

Linking words is a game from [wordsword](https://github.com/Schubaru/wordsword). Everything in `play/` is copied
unchanged from wordsword's `docs/play/`, so the two sites play the same board each day.
When wordsword changes the game or its word bank, copy it across again (from this folder, wordsword checked out
beside it):

```sh
W=../wordsword/docs/play
cp $W/{linking.js,logic.js,play.js,rng.js,play.css} play/
cp -R $W/fonts play/
cp $W/data/linking-words.txt play/data/
```

Only `index.html`, the icons and `og.png` belong to this site. `art/art.html` draws the icons and the
link-preview card; the commands to render them are at its top.

## Playing a set day

On localhost, `?day=N` plays day N: `python3 -m http.server 8000`, then open `http://localhost:8000/?day=3`.
Saved games live in the browser (`localStorage`), so they're separate from wordsword's.
