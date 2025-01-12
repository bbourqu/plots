# Digital Garden

### Commands

All commands are run from the root of the project, from a terminal:

| Command             | Action                                             |
| :------------------ | :------------------------------------------------- |
| `pnpm install`      | Installs dependencies                              |
| `pnpm dev`          | Starts local dev server at `localhost:4321`        |
| `pnpm build`        | Build your production site to `./dist/`            |
| `pnpm preview`      | Preview your build locally, before deploying       |
| `pnpm astro ...`    | Run CLI commands like `astro add`, `astro preview` |
| `pnpm astro --help` | Get help using the Astro CLI                       |

## Integrations

### UnoCSS

In this theme, I'm using [UnoCSS](https://uno.antfu.me/) to generate the CSS. 

### Sitemap

To generate the sitemap, you don't need to do anything.

```js title="astro.config.mjs"
import { defineConfig } from 'astro/config';

export default defineConfig({
  site: 'https://example.com',
});
```

### RSS

The RSS feed is automatically generated from the Markdown files in the `src/content/blog` folder. You can of course 
completely change this to your own needs.

The RSS will output to `https://example.com/feed.xml` by default. You can change this, 
by renaming `src/pages/feed.xml.js`.

## Components

### `components/blog/`

This directory contains all components for the blog.

### `components/errors/`

This directory contains all error components.

#### `components/errors/404.astro`

This component is used when a page is not found.

### `components/generic/`

This directory contains all generic components, reused over multiple pages.

### `components/home/`

This directory contains all components for the home page.

### `components/layout/`

This directory contains all layout components. For instance, the header and footer and `<head>` section.