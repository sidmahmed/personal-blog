## Commands

| Command        | Action                                       |
| :------------- | :------------------------------------------- |
| `pnpm install` | Installs dependencies                        |
| `pnpm dev`     | Starts local dev server at `localhost:3000`  |
| `pnpm build`   | Build your production site to `./dist/`      |
| `pnpm preview` | Preview your build locally, before deploying |

## Configure

- Edit config file `src/site-meta.config.ts` for basic site meta data
- Update file `astro.config.mjs` site property with your own domain
- Replace & update files within the `/public` folder:
  - favicon.ico
  - `/images` folder - add your own icon
  - robots.txt - update the Sitemap url to your own domain
  - manifest.webmanifest
- Modify file `src/styles/global.css` with your own light and dark styles
- Create / edit posts for your blog within `src/pages/posts/` with .md file(s)
- Optional:
  - Fonts: This theme sets the body element to the font family `font-mono`, located in the global css file `src/styles/global.css`. You can change fonts by removing the variant `font-mono`, after which TailwindCSS will default to the `font-sans` [font family stack](https://tailwindcss.com/docs/font-family).

## Adding posts

Adding a post is a simple as adding your .mdx file(s) to the `src/pages/posts/` folder, the name of which will be used as the slug/url. The two posts included with this template can be modified, and give you an example of how to structure your posts. [Astro docs](https://docs.astro.build/en/guides/markdown-content/) also has a detailed section on markdown pages.

### Frontmatter

| Property (\* required) | Description                                                                                                                                                                                   |
| :--------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| layout                 | This is used to import [Markdown Layouts](https://docs.astro.build/en/core-concepts/layouts/#markdown-layouts), this theme uses `src/layouts/BlogPost.astro` as a wrapper for all blog posts. |
| title \*               | Self explanatory. Used as the text link to the post, the h1 on the posts' page, and the pages' title property                                                                                 |
| description \*         | Similar to above, used as the seo description property                                                                                                                                        |
| publishDate \*         | Again pretty simple. To change the date format/locale, currently **en-GB**, update/pass the **locale** arg to function **getLocaleTime**, found in `src/util.ts`.                             |
| tags                   | Tags are optional. Any new tag(s) will be shown in `yourdomain.com/posts` + `yourdomain.com/tags`, and generate the page(s) `yourdomain.com/tags/[yourTag]`                                   |
