# shiplean.app

The landing page for **ShipLean**, the free, open-source, self-hosted planning tool: backlogs, boards and sprints with a forecast that tells you what fits. It is a single static page that says what ShipLean is and that it is open source and coming soon.

| Folder | What it is |
|---|---|
| [`site/`](site/) | The website. Plain HTML and CSS with no build step: `index.html`, `tokens.css`, `favicon.svg`, `og-image.png` and the screenshots in `shots/`. |
| [`design/`](design/) | Reference assets: logo and favicon, design tokens, full-resolution screenshots of every screen in light and dark, and the social card source. See [`design/README.md`](design/README.md). |

## Run it locally

Open `site/index.html` in a browser, or serve the folder:

```sh
npx serve site
```

## Deploy

Merging to `main` publishes the site. [`.github/workflows/deploy.yml`](.github/workflows/deploy.yml) uploads `site/` to the Cloudflare Pages project `shiplean`, which serves `shiplean.app` and `www.shiplean.app`. It runs when something under `site/` or the workflow itself changes, and you can also start it by hand from the Actions tab.

The workflow needs two repository secrets: `CLOUDFLARE_API_TOKEN`, a token with **Account → Cloudflare Pages: Edit**, and `CLOUDFLARE_ACCOUNT_ID`.

To deploy by hand with the same token in your environment:

```sh
npx wrangler pages deploy site --project-name shiplean --branch main
```

## Editing the page

- Colours, fonts and radii come from `site/tokens.css`, a copy of the ShipLean app's design tokens. Change the page's look there or in the `<style>` block in `index.html`, not with one-off hex values.
- Every screenshot exists in light and dark. The page shows the one that matches the visitor's theme, so add or replace both.
- Links to GitHub point at the [`shiplean`](https://github.com/shiplean) org. Point them at the app repo once it is public.
