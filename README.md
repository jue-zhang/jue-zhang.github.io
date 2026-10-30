# Jue Zhang's personal website

Live site: <https://jue-zhang.github.io>

Built with [Academic Pages](https://academicpages.github.io/) and Jekyll.
The upstream theme's MIT license and attribution are preserved.

## Updating the site

- Edit `_pages/about.md` for the homepage and biography.
- Edit `_pages/publications.md` for selected publications.
- Edit `_config.yml` for sidebar details and profile links.
- Edit `_data/navigation.yml` for the navigation.
- Replace `images/profile.svg` with an approved portrait and update
  `author.avatar` in `_config.yml` when a photograph is available.

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

The site initially contains About and Publications pages. Add talks, blog posts,
or a public CV when content is ready; removed template samples are not personal
content.
