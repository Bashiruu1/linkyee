# Bashiruu1 Link Page

A small GitHub Pages link page built from the open-source
[linkyee](https://github.com/ZhgChgLi/linkyee) template.

This repository keeps the static-site generator, theme, and GitHub Actions
deployment from linkyee, but the README and default configuration are scoped to
this project instead of the upstream demo.

## Local Development

Install the Ruby dependencies:

```sh
bundle install
```

Generate the site into `_output/`:

```sh
bundle exec ruby scaffold.rb
```

Open `_output/index.html` in a browser to review the generated page.

## Configuration

Edit [config.yml](./config.yml) to update:

- page title, display name, tagline, footer, and copyright
- visible links under `links`
- social links under `socials`
- optional analytics ID under `google_analytics_id`

The default config intentionally starts with a small Bashiruu1 GitHub profile
link instead of upstream template links. Add more links as the public page
needs them.

## Deployment

GitHub Actions builds the page and publishes the generated files to the
`gh-pages` branch.

For first-time setup:

1. In repository settings, enable GitHub Actions for this repository.
2. Set workflow permissions to `Read and write permissions`.
3. In Pages settings, select the `gh-pages` branch as the publishing source.
4. Push a change to `main`, then wait for the `Automatic build` workflow.

The workflow can also run on its daily schedule so plugin-generated values stay
fresh. Remove the `schedule` block in `.github/workflows/build.yml` if scheduled
redeploys are not needed.

## Customization

Theme files live under `themes/default/`:

- `index.html`
- `styles.css`
- `scripts.js`

To add a new theme, create `themes/YOUR_THEME/` and set `theme: YOUR_THEME` in
`config.yml`.

## License

This project keeps the upstream MIT license. See [LICENSE](./LICENSE).
