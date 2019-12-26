---
title: A flexible way to build your site URLs
layout: post
tutorial: true
author: Mahmud
image: assets/images/2239751569.jpg
---

We have a /blog.html page and want the URL on the live site to be /blog/. One way we could do this is create a new folder called blog, move blog.html in that folder and then rename it to index.html. The problem with this is we’re creating folders just to have the URLs we want. Let’s move /blog/index.html back to /blog.html and solve this with permalinks. We can add a permalink in front matter, then we just need to specify the URL we want:


What if we wanted to set a permalink for all our blog posts? We could add a permalink to every blog post but that could take forever. A better way is to set it once for all blog posts in _config.yml. The variables available to us when setting permalinks for posts are as follows: