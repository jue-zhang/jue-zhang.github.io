# Jue Zhang's personal website

Live site: <https://jue-zhang.github.io>

Built with [Academic Pages](https://academicpages.github.io/) and Jekyll.
The upstream theme's MIT license and attribution are preserved.

## Updating the site

- Edit `_pages/about.md` for the homepage, biography, honors, and professional
  service. Keep experience and award claims grounded in the approved CV;
  link public coverage where relevant and label non-English articles.
- Edit `_data/publications.yml` for selected publications grouped by research area.
  They appear on the About page through `_includes/selected-publications.html`.
  Entries render newest first within each area using `sort_key`: publication
  year (preprint year for unpublished work), followed by the arXiv identifier
  to break ties within a year. For papers without an arXiv ID, use `0000.00000`
  as the tie-breaker; no within-year publication date is claimed.
  Each entry records its full
  title, complete ordered author list in `authors` (with `Jue Zhang` rendered
  in bold), confirmed venue and year (or arXiv identifier for preprints), arXiv
  identifier when available, and official GitHub repository when verified.
  Keep evidence links in the `sources` field; those are not rendered on the page.
  Verify author order against the published version when available, otherwise
  the preprint; retain the author metadata URL in `author_source`.
  AutoSaddler uses the complete 13-author arXiv manuscript list, corroborated
  by its project page, rather than the NeurIPS poster's shorter author metadata.
  Do not invent an arXiv link for a paper available only from its publisher.
  Add verified media coverage beside a paper with `media_url` and `media_label`.
- Edit `_data/research.yml` for featured themes. These reference the existing
  publication records by arXiv ID; titles, authors, venues, and resources stay
  in `_data/publications.yml`. All selected publications appear once, grouped
  by research area and sorted newest first, without a separate highlights list.
- Set `internships_open: false` in `_config.yml` to hide the internship callout.
- Edit `_config.yml` for sidebar details and profile links.
- Edit `_data/navigation.yml` for the navigation.
- The approved portrait is `images/profile.jpg`; `author.avatar_caption` in
  `_config.yml` supplies the short note directly beneath it. Remove location
  metadata before replacing the photo.

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

## Research refresh review preview

The `users/jue/research-homepage-preview` branch is for review only. It is not
merged into `master`. Manually run the existing Pages workflow on this branch:

```sh
gh workflow run jekyll.yml --ref users/jue/research-homepage-preview
```

On a non-default branch, the workflow builds the unchanged `master` homepage
and puts the candidate under `/preview/research-refresh/` in the same deployment.
The preview uses `_config.preview.yml`, including a preview base URL and
`noindex, nofollow`; the original homepage keeps its existing content and assets.
Both builds use the same Gemfile and dependency lockfile.
The GitHub Pages environment must allow this exact review branch to deploy.
A subsequent normal `master` deployment removes the temporary preview.
Do not merge the review branch or replace the main homepage until approved.

For a local preview using the same base path:

```sh
JEKYLL_ENV=production bundle exec jekyll build --strict_front_matter \
  --config _config.yml,_config.preview.yml \
  --destination /tmp/jue-review-site/preview/research-refresh
```

Serve `/tmp/jue-review-site` using a static server and open
`/preview/research-refresh/`. Check light/dark mode, a 390px mobile viewport,
keyboard navigation, and featured-paper anchors.

Pending information: no public-safe CV PDF has been supplied, so there is no
CV placeholder link. The private CV is not published. ParetoSaddler is omitted
until an official public paper or project URL is verified.
