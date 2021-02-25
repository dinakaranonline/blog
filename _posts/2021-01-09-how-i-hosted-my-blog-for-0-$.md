---
title: How I hosted my blog for 0$
date: 2021-01-09 00:00:00 Z
categories:
- General
- Technology
layout: post
author: dinakaran
image: assets/images/blog-hosting.jpeg
---

When I wanted to set up my new personal blog, I was looking for various options. I had prior experience setting up my blog, right from my earlier days in platforms like Blogger, WordPress etc. So I did not want to use WordPress or Blogger as it felt way too easy. Last time I checked, custom domain name mapping costs some money. Also, the self-hosted option would need a database, and it may be costly to set up and host.

The second option I thought about was Medium since it was widely popular, and most of the blog these days are hosted in Medium. But Medium had tried to push monetization and introduced paywall. So I had to look elsewhere. Another option to was to use LinkedIn. Again it is easier to set things up, but be at the mercy of another distribution platform.

**Mark Down, Static Site Generator and GitHub Pages to the rescue**

So I was exploring other options, and then I came with this option of Markdown and GitHub Pages. It was a pretty quirky combination of different tools and technologies coming together.

- Markdown is a lightweight markup language for creating formatted text using a plain-text editor.

- Static Site Generator is an easy way to develop sites like blogs and personal websites using Markdown.

- GitHub Pages is an extension of GitHub. GitHub allows public repositories to be created and managed free of cost. GitHub Pages offers simple and easy ways to host static websites for free. It acts as a platform with the storage, static file hosting and, CI-CD process - all seamlessly integrated as a full-fledged PAAS solution. I love the vision of GitHub.

- To create blog posts, I used prose.io that offers a simple interface to blog. Prose is a content editor for GitHub designed for managing websites. All the posts and content created will be stored in GitHub repository.

So I used a combination of Jekyll Static Site Generator to set up the blog, Prose Markdown editor and GitHub Pages as a hosting platform to set up my blog. 

I bought a personal domain from Google and mapped it to the blog. With all this setup, I did not have to spend any money for hosting the blog.

**What I learnt from the experience**

- Loved the whole exploration of figuring it out and setting up things.

- Whole process was not that seamless as I expected it to be.

- Blogging workflow is not optimal. It takes more time to make things work. 

- Distribution is decent, but not good. Posting in LinkedIn and Twitter has better reach than this.
 
Despite all this, I was happy with the whole setup. I could understand how the entire thing came together - be it various layouts, look and feel, data and other things working in the background to finally render the blog. There was an option to configure Google Analytics as well and track the performance of the site. 

This whole experience helped me appreciate the design and technical/system architecture. Every blog post is like a code commit and entire CI-CD process running to deploy the latest code.

Since I have absolute control with the actual source, it was easy to create or customize the site however I want. I played quite a bit of time tweaking configuration here and there. Sometimes I loved the technical aspect of setting up a blog instead of the actual blogging experience itself. 

So with this setup, I have managed to host my blog without spending a single dollar.  

**Tools Used:**

- Git Hub Pages: Hosting the static website 

- Jekyll: Static Site Generator for blogs 

- Prose: Content Editor for GitHub

