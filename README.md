# kwuang.me

### Dev

```bash
yarn
yarn serve # hot-reload
yarn debug # debug
```

Install [Nunjucks VSCode extension](https://marketplace.visualstudio.com/items?itemName=eseom.nunjucks-template#overview)

### Thought about using a CMS

- tried Git-based CMS that could output Markdown: Netlify CMS, Forestry.io, but both didn't give enough improvements over content management than just plain Markdown. Their main advantage were being able to go to `/admin` and just edit content right in your web browser.
  - Since I'm planning on just devving locally, I get content previews via 11ty's hot-reload
  - for WYSIWYG, can just use **https://typora.io/** (which also comes with word count, focus mode, auto pair, outline panel)

### Implementation Notes

- `about/index.md` shows how to add a content page.
- `posts/` has the blog posts but really they can live in any directory. They need only the `post` tag to be added to this collection.
- Add the `nav` tag to add a template to the top level site navigation. For example, this is in use on `index.njk` and `about/index.md`.
- main config in `./eleventy.js`
  - Content can be any template format (blog posts needn’t be markdown, for example). Configure your supported templates in `.eleventy.js` -> `templateFormats`. \* Because `css` and `png` are listed in `templateFormats` but are not supported template types, any files with these extensions will be copied without modification to the output (while keeping the same directory structure).
- The blog post feed template is in `feed/feed.njk`. This is also a good example of using a global data files in that it uses `_data/metadata.json`.
- This example uses three layouts:
  - `_includes/layouts/base.njk`: the top level HTML structure
  - `_includes/layouts/home.njk`: the home page template (wrapped into `base.njk`)
  - `_includes/layouts/post.njk`: the blog post template (wrapped into `base.njk`)
- `_includes/postlist.njk` is a Nunjucks include and is a reusable component used to display a list of all the posts. `index.njk` has an example of how to use it.
