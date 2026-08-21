# zfying.github.io

Source for my personal academic website: https://zfying.github.io/

A single static page (`index.html`) served by GitHub Pages. All styles and the
publication-filter script are inline — there is no build step. To preview
locally, open `index.html` in a browser or run `python3 -m http.server`.

## Layout

```
index.html            the entire site
images/               profile photo, paper thumbnails, institution logos (WebP)
favicon.png           48x48 tab icon
apple-touch-icon.png  180x180 home-screen icon
```

## Adding a publication

Copy an existing `.publication-card` block in `index.html` and update the title,
authors, venue, and links. Give it one or more `.label` spans — the labels drive
the filter buttons at the top of the Research section, so the label text must
match a button's `data-filter` value exactly.

## Images

Thumbnails are WebP, sized for their display box: 600px wide for paper figures,
150px for logos, 500px for the profile photo. Convert new images before
committing so the page stays light:

```sh
cwebp -q 82 -metadata none -resize 600 0 figure.png -o images/paper_name.webp
```

Set `width`, `height`, and `loading="lazy"` on the `<img>` tag to avoid layout
shift.

## Credit

Template adapted from [Jon Barron's website](https://jonbarron.info/).
