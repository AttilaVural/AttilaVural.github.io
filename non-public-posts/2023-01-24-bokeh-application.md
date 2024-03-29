---
layout: post
title:  "Bokeh server application embedded in a static page"
date:   2023-01-24 15:00:00 +0000
categories: Code
mermaid: true
---

You do not need flask, as bokah has its own inbuilt web server.

Three ways to do this:
Server side rendered pages.
Server side rendered but embedded on a static page.
Completely client side -  you won't be able to use the browser of your clients to scrape content from other websites using JavaScript because of a security measure called Same-origin policy (https://developer.mozilla.org/en-US/docs/Web/Security/Same-origin_policy).

<div class="mermaid">
graph LR
    A[Struct]
        A---B1[test]
</div>
