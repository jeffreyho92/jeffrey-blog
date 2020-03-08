---
title: hexo
date: 2016-04-29 09:21:34
tags: hexo
category:
---

# hexo 3

```bash
hexo clean
```

```bash
hexo generate / hexo g
```

```bash
hexo deploy / hexo d
```

Short cut:
```bash
hexo g -d
```

## Static Sidebar

```bash
grep -rl 'displaySidebar' themes/next/
```

### comment the code

themes/next/source/js/src/motion.js
```js
sidebar: function (integrator) {
  //if (CONFIG.sidebar.display === 'always') {
    NexT.utils.displaySidebar();
  //}
  integrator.next();
}
```

themes/next/source/js/src/post-details.js
```js
NexT.motion.middleWares.sidebar = function () {
    var $tocContent = $('.post-toc-content');

    //if (CONFIG.sidebar.display === 'post' || CONFIG.sidebar.display === 'always') {
      if ($tocContent.length > 0 && $tocContent.html().trim().length > 0) {
        NexT.utils.displaySidebar();
      }
    //}
};
```

```bash
hexo g -d
```

## add-on for hexo

```bash
npm install hexo-generator-feed --save
npm install hexo-generator-sitemap@1.0.0 --save
```

__dir/_config.yml
```yml
theme: next

sitemap:
  path: sitemap.xml

feed:
  path: atom.xml
```

```bash
npm update
hexo g -d
```

## NexT theme

```js
# Schemes
scheme: Muse
# Sidebar
display: always

avatar:
  /images/avatar.png

highlight_theme: night eighties
```

```bash
hexo clean
hexo g -d
```

```bash
hexo new page "tags"
```

tags\index.md
```
title: All tags
date: 2014-12-22 12:39:04
type: "tags"
---
```

themes/_config.yml
```
menu:
  home: /
  archives: /archives
  tags: /tags
```