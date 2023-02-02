---
title: Black Market Example Post
publishDate: 1 Feb 2023
author: The Plug
authorURL: https://theplugblog.netlify.app/
description: Black Market Example Post
layout: ../../layouts/BlogPost.astro #todo @ layout: create BlackMarketPost layout
---
[Netlify CMS](https://www.netlifycms.org/) is an open-source, Git-based content management system. It provides a single-page app for editing content and can publish that content by committing it to a hosted Git repo (for example on GitHub or GitLab).

Adding Netlify CMS to an [Astro](https://astro.build/) site would usually involve creating a number of files in different parts of your project directory and then keeping all those moving parts in sync. With the [`astro-netlify-cms`](https://github.com/delucis/astro-netlify-cms/) integration, you configure the integration in your `astro.config.mjs` file and the integration takes care of the rest.

![Astro + Netlify CMS logos](/assets/blog/header.png)

```javascript
import { defineConfig } from 'astro/config';
import NetlifyCMS from 'astro-netlify-cms';

export default defineConfig({
  integrations: [
    NetlifyCMS({
      config: {
        backend: {
          name: 'git-gateway',
          branch: 'main',
        },
        collections: [
          // Content collections
        ],
      },
    }),
  ],
});
```