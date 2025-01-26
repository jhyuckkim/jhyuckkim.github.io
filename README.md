# Junhyuck Kim's website

Jekyll personal website hosted on GitHub Pages.

## Local preview

With Ruby 3.3.3 installed through rbenv:

```sh
RBENV_VERSION=3.3.3 rbenv exec gem install jekyll webrick
RBENV_VERSION=3.3.3 rbenv exec jekyll serve --livereload
```

Open http://127.0.0.1:4000. Stop with Ctrl+C. Restart the server after changing `_config.yml`.

## Content

- Publications and blog entries: `_data/publications.yaml`.
- Profile links: `_data/main_info.yaml`.
- CV: add the PDF under `assets/cv/`, then set `cv` to its path (for example `/assets/cv/Junhyuck-Kim-CV.pdf`). An empty value keeps the unlinked CV placeholder.
- Blog metadata: use `title` and `description` in the post front matter. Optional `image` and `image_alt` override the default profile photo used in sharing previews.

Internal links open in the current tab; external research links open in a new tab. Generated `_site/` output and Jekyll caches are ignored by Git.

## Visitor analytics

Create a GoatCounter account at https://www.goatcounter.com/ and set
`goatcounter_code` in `_data/main_info.yaml` to the site code from your
`https://YOURCODE.goatcounter.com` address. This code is public, not a password.
Keep the dashboard private and individual pageview collection disabled.
Analytics loads only in production builds with a nonempty code; local previews
and the default blank setting do not load the tracking script.
GoatCounter provides aggregate pageviews, referrers, and device/location statistics
without visitor cookies. See https://www.goatcounter.com/help/privacy for details.

## Build

```sh
JEKYLL_ENV=production RBENV_VERSION=3.3.3 rbenv exec jekyll build --disable-disk-cache
```

Local changes are not published until committed and pushed through the site's GitHub Pages workflow.
