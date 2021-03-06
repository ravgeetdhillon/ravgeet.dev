---
title: Adding pages to Jekyll site
date: 2019-07-19 14:00:00 +0530
categories: jekyll web-dev
description: Adding pages to the Jekyll site is pretty simple. In this blog, I share with you some important steps on how to add pages to a documentation website, but the method is universal to any website you want.
img: adding-pages-to-jekyll-site.jpg
img_credits: Photo by [Lilly Rum](https://unsplash.com/@rumandraisin) on [Unsplash](https://unsplash.com)
---

This is tutorial can be used to add pages to any Jekyll site. I am assuming that you have setup your Ruby Development Environment. If not, then refer to this document here to get started easily.

Below are few easy steps that you can follow to add pages to your Jekyll site. I have also attached images to explain the process better.

*Note: I have taken the example of [GTK Website][gtk-website], I'm working on. You can find it's Gitlab instance [here][gitlab-repo].*

### Step 1.
In `collections/_docs` directory, create a new file with name: `hello-world.md`.

![Creating a new Markdown file.](/assets/img/blog/adding-pages-to-jekyll-site-screen-1.png)

### Step 2.
I want this page to be available at the following link: [http://localhost:4000/docs/tutorials/hello-world/](http://localhost:4000/docs/tutorials/hello-world/)

Add the following front matter to the `hello-world.md`.
```
---
permalink: /docs/tutorials/:name/
---
```

![Adding the front matter to the Markdown file.](/assets/img/blog/adding-pages-to-jekyll-site-screen-2.png)

### Step 3.
Add your content in the Markdown format to the `hello-world.md.

```
This is the demo file to show the process of adding new pages to a Jekyll site.
```

![Adding the new content to the Markdown file.](/assets/img/blog/adding-pages-to-jekyll-site-screen-3.png)

### Step 4.
In `_data` directory, open the `navigation.yml` file and update the sidebar_links array by adding the following content:

```
- title: Hello World
  name: hello-world
  section: Tutorials
```

here,
* `title` is display text on sidebar on `docs` page
* `name` is the name of the file which should be pointed to when the link is accessed
* `section` is category this page should fall under

![Updating YML file in the Jekyll Project.](/assets/img/blog/adding-pages-to-jekyll-site-screen-4.png)

### Step 5.
In case the new file is the main section page, then update the sidebar_sections array by adding the following content:
```
- title: Tutorials
  name: tutorials
```
here,
* `title` is display text on sidebar on `docs` page
* `name` is the name of the file which should be pointed to when the link is accessed

![Updating YML file in the Jekyll Project.](/assets/img/blog/adding-pages-to-jekyll-site-screen-5.png)

### Step 6.
Save all the files and serve the website on the local server by running the following command.
```
bundle exec jekyll serve
```

![Compiling the Jekyll website.](/assets/img/blog/adding-pages-to-jekyll-site-screen-6.png)

### Step 7.
Go to [http://localhost:4000/docs/tutorials/hello-world/](http://localhost:4000/docs/tutorials/hello-world/) and the page is up and running.

[gtk-website]: https://ravgeetdhillon.pages.gitlab.gnome.org/gtk-web/
[gitlab-repo]: https://gitlab.gnome.org/ravgeetdhillon/gtk-web

![Fetching the Jekyll website on the localhost.](/assets/img/blog/adding-pages-to-jekyll-site-screen-7.png)

![Fetching the Jekyll website on the localhost.](/assets/img/blog/adding-pages-to-jekyll-site-screen-8.png)

Lemme know if you have any doubt, appreciation or anything else that you would like to communicate to me. You can tweet me [@ravgeetdhillon](https://twitter.com/intent/tweet?screen_name=ravgeetdhillon&original_referer={{ page.url | prepend: site.url }}&ref_src=twsrc%5Etfw). I reply to all the questions as quickly as possible. 😄 And if you liked this post, please [share](https://twitter.com/intent/tweet?text={{ 'Check out this amazing blog post by Ravgeet Dhillon sharing his thoughts on ' | append: page.title | urlencode }}&screen_name=ravgeetdhillon&original_referer={{ page.url | prepend: site.url }}&ref_src=twsrc%5Etfw) it with your twitter community as well.