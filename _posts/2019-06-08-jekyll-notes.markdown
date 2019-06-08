---
layout: post
title:  "Notes for Using Jekyll and Git"
date:   2019-06-08 15:15:00 -0400
categories: jekyll
---

## Helpful Links
Quick Start for everything  
<https://medium.com/@chantil/quick-tutorial-build-a-blog-on-github-pages-with-jeykll-20f7d2ad0b06>  

How to use Jekyll on Github-Pages  
<https://help.github.com/en/articles/using-jekyll-as-a-static-site-generator-with-github-pages>  
<https://help.github.com/en/articles/adding-a-jekyll-theme-to-your-github-pages-site>  

The leap-day theme seems really nice, planning on trying it next. Found it from <https://pages.github.com/themes/>.  
<https://github.com/pages-themes/leap-day>  

## Jekyll Commands
```
$ gem install jekyll bundler     # install bundler and Jekyll
$ jekyll yourname.github.io       # create a new site
$ cd yourname.github.io
$ bundle exec jekyll serve       # run real-time build on local server, available at 127.0.0.1:4000
$ bundle update                 # build site for publishing to remote server
```

## Common Git commands for uploading to Github Pages
Stage changes to local repo  
`git add .`  
-or-  
`git add --all`

Commit to local repo with comment  
`git commit -m "Initial commit"`  

Push to remote repo, assuming it was cloned from a remote repo  
`git push -u origin master`  
`-u` is commonly used for first push from a local repo to a remote. For every branch that is up to date or successfully pushed, add upstream (tracking) reference, used by argument-less git-pull[1] and other commands. For more information, see branch.<name>.merge in git-config[1].  
