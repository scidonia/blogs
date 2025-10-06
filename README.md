## Blog
The website features a simple markdown blog. It uses markdown files rather than a database.

Blogs for BookWyrm live in the /posts directory.

To create a blog follow the instructions below:

### Creating a new blog

1. Checkout in a branch to work on your blog draft.

2. Create a .md file in the posts directory

3. Ensure you fill in the post Yaml-like properties. This sets things like post title, header image, slug, author, and extract. Without this information, the post will be omitted. The post information looks like this:

```markdown
---
title: "The Future of AI Data Management"
slug: "futre-of-ai-data-management"
excerpt: "AI is rapidly automating cognitive labour, transforming workplaces. Effective data management is crucial, yet much tacit knowledge remains undocumented, causing inefficiencies and challenges during staff transitions."
coverImage: "/blog/the-future-of-ai-data-management.webp"
category: "Data Management"
date: "2025-03-17T10:23:07.322Z"
author:
  name: Gavin
  picture: "/blog/letter-g.png"
ogImage:
  url: "/blog/the-future-of-ai-data-management.webp"
---
```

3. Images need to be saved in the public/blog directory of the BookWyrm dashboard repo and then linked with a relative link, e.g. `/blog/the-future-of-ai-data-management.webp`

4. Images in the post body should be used like: `![Robot AI obtaining context from data](/blog/ai-agent-obtaining-context.webp)`

5. I have saved some letter-based avatars for G & M in the public/blog directory for author images. `/blog/letter-g.png` & `/blog/letter-m.png`
