# mind the process

the grassnose blog at [www.grassno.se](https://www.grassno.se). a small jekyll
site: one stylesheet, self-hosted fonts, no javascript.

## run locally

```sh
bundle install
bundle exec jekyll serve
```

## write a post

add an html file to `_posts/` named `YYYY-MM-DD-slug.html`:

```yaml
---
layout: post
title: 'title'
subtitle: 'optional subtitle'
date: YYYY-MM-DD HH:MM:SS -0400
image: '/img/posts/NN.jpg'  # cover, home tile, and share preview
---
```

then make the home-page tile for the new image (needs pillow):

```sh
python3 bin/thumbs
```

skipping this still works; the home page falls back to the full-size image.

embed a video with the `video` tag (see `_plugins/video_tag.rb`) and audio with
`{% include embed-audio.html src="..." %}`. give every `<img>` an `alt`.

## notes

- `timezone: UTC` in `_config.yml` keeps post permalinks matching the live
  site. changing it can move a post's date-based url.
- fonts are DotGothic16 and Lora (latin subsets), both under the SIL open font
  license; see `assets/fonts/`.
