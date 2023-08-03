---
title: A Blog
description: |
  This is a fully featured blog that supports categories, 
  tags, series, and pagination.
author: "Adam Bozman"
show_post_thumbnail: true
show_author_byline: true
show_post_date: true
# for listing page layout
layout: list-sidebar # list, list-sidebar, list-grid

# for list-sidebar layout
sidebar: 
  title: A Digital Garden
  description: |
  
    I wanted a space for my abstract and unpublished thoughts - something of a working draft site, which this blog now is.  I've had a number of colleagues and friends offer that journaling is both productive and theraputic.  Therefore, I mostly write about potential research topics and things I find important - both postive and negative.
    
    I try to emulate and follow the ethos of Maggie Appleton's [Digital Garden](https://maggieappleton.com/garden-history).
    
#    Check out the _index.md file in the /blog folder 
#    to edit this content. 
  author: "Adam Bozman"
  text_link_label: # Subscribe via RSS
  text_link_url: /index.xml
  show_sidebar_adunit: false # show ad container

# set up common front matter for all pages inside blog/
cascade:
  author: "The R Markdown Team @RStudio"
  show_author_byline: true
  show_post_date: true
  show_disqus_comments: false # see disqusShortname in site config
  # for single-sidebar layout
  sidebar:
    text_link_label: View recent posts
    text_link_url: /blog/
    show_sidebar_adunit: false # show ad container
---

** No content below YAML for the blog _index. This file provides front matter for the listing page layout and sidebar content. It is also a branch bundle, and all settings under `cascade` provide front matter for all pages inside blog/. You may still override any of these by changing them in a page's front matter.**