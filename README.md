# Blog

With Svelte!

## Dev

All of your posts are in `/posts`. You can add a new post by creating a new folder with an index.md file.

```
/posts/my-first-post/index.md
```

Make sure your posts have `title` and `date` properties in the frontmatter.

```md
---
title: My First Post
date: 2021-07-09
---

(your content here)
```

Each individual post is rendered at `src/routes/posts/[slug].svelte`. You can access all frontmatter data as props here. You'll notice some basic meta tags setup for SEO and social media sharing, including a generated open graph image (courtesy of [og-image.vercel.app](https://og-image.vercel.app)).

![open-graph](https://og-image.vercel.app/**Getting%20Started**?theme=light&md=1&fontSize=100px&images=https%3A%2F%2Fassets.vercel.com%2Fimage%2Fupload%2Ffront%2Fassets%2Fdesign%2Fhyper-color-logo.svg)

If you're unfamiliar with mdsvex, I would recommend [looking at the website](https://mdsvex.com/playground) to see what is all possible out of the box.

You can change the theme by editing `src/prism.css`, or [replacing it with one of the many available themes](https://github.com/PrismJS/prism-themes/tree/master/themes).

See [here](https://github.com/tailwindlabs/tailwindcss-typography) for typography & styling.

### MDSvex

The mdsvex plugins support extra features, see the `mdsvex.config.js` file. 
The [mdsvex-relative-images](https://github.com/mattjennings/mdsvex-relative-images) plugin allows us to load images or videos using a relative URL. This is particularly nice for keeping images grouped with their post folder, rather than needing to put them in `/static`.
[remark-reading-time](https://github.com/mattjennings/remark-reading-time) adds the estimated reading time to the post's frontmatter.
[remark-preview](https://github.com/mattjennings/remark-preview) provides snippets for each post in their frontmatter. 
The `preview` frontmatter property contains plain-text (which we use for SEO), and `previewHtml` contains formatted HTML (which we use to preview to the user). 
eware that the preview content does not run through mdsvex, so mdsvex-specific features and plugins will not work in preview (such as components, or relative images unfortunately).
