# SPCoast.github.io
Documentation repo for SPCoast Electronics Projects (Jekyll/GitHub Pages).

Live site: https://SPCoast.github.io

## Local development
- Install Ruby (3.2+) and Bundler
- Install gems: `bundle install`
- Serve locally: `bundle exec jekyll serve`

## Build & deploy (GitHub Actions)
- Site builds via `.github/workflows/jekyll.yml`
- On push to the default branch, Actions runs `bundle exec jekyll build` and deploys to GitHub Pages
- If you see build failures, check workflow logs under the Actions tab

## Content structure
- Project overviews live in `pages/`
- Versioned project docs live in `_versions/<ProjectName>/<X.Y>.md`
- Arduino sketches live in `_sketches/`

Notes
- Front matter must be valid YAML. If a `tagline` contains a colon (`:`), wrap the value in quotes.
- Images referenced in front matter should use absolute paths under `/versions/...`.
