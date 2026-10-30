# Jue Zhang's personal website

Live site: <https://jue-zhang.github.io>

Built with [Academic Pages](https://academicpages.github.io/) and Jekyll.
The upstream theme's MIT license and attribution are preserved.

## Updating the site

- Edit `_pages/about.md` for the homepage and biography.
- Edit `_data/publications.yml` for selected publications grouped by research area.
  They appear on the About page through `_includes/selected-publications.html`.
  Entries render newest first within each area using `sort_key`: publication
  year (preprint year for unpublished work), followed by the arXiv identifier
  to break ties within a year. For papers without an arXiv ID, use `0000.00000`
  as the tie-breaker; no within-year publication date is claimed.
  Each entry records its full
  title, confirmed venue and year (or arXiv identifier for preprints), arXiv
  identifier when available, and official GitHub repository when verified.
  Keep evidence links in the `sources` field; those are not rendered on the page.
  Do not invent an arXiv link for a paper available only from its publisher.
- Edit `_config.yml` for sidebar details and profile links.
- Edit `_data/navigation.yml` for the navigation.
- The approved portrait is `images/profile.jpg`; the homepage includes its
  personal anecdote. Remove location metadata before replacing the photo.

Push changes to `master`. The **Deploy personal website to Pages** workflow
builds the site and publishes it through GitHub Pages. Deployment status is
available in the repository's Actions tab.

Only public research and approved biographical information belong in this
repository. Do not upload private manuscripts, internal notes, or a CV containing
personal contact information without first preparing a public version.

## Local preview

With Ruby 3.3 and Bundler installed:

```sh
bundle install
bundle exec jekyll serve --host 127.0.0.1
```

Open <http://127.0.0.1:4000>. To validate a production build:

```sh
JEKYLL_ENV=production bundle exec jekyll build --strict_front_matter
```

The About page includes selected publications. The old `/publications/` address
redirects to that section. Add talks, blog posts, or a public CV when content is
ready; removed template samples are not personal content.

The public footer banner is intentionally omitted from the default layout.
Upstream theme attribution and the MIT license remain in this repository.
