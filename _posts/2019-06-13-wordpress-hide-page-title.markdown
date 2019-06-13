---
layout: post
title:  "Howto Remove Page Titles from Wordpress Page"
date:   2019-06-08 18:23:00 -0400
categories: wordpress
---

## Helpful Links
How to Hide the Page Title in WordPress  
<https://www.webhostinghero.com/blog/how-to-hide-the-page-title-in-wordpress/?PageSpeed=noscript>  

Add Unique Custom Styles to One WordPress Page or Post  
<https://amethystwebsitedesign.com/add-unique-custom-styles-to-one-wordpress-page-or-post/>  

## General Process

### PHP Method
Using WordPress hooks, I can change it to whatever I like or even remove it completely. We’re looking for a solution that has the following properties:

    Works on all themes;
        Doesn’t require a plugin;
            “Plug and Play”.

            I prefer not to install plug-ins if I can avoid them. They quickly become unmanageable and when the function is highly specific, I prefer to write a snippet of code myself. In this situation, we’re going to make use of a WordPress filter known as “the_title”. In your functions.php file or in the place where you normally keep your custom PHP code, copy and paste the following snippet:

            function change_the_title( $title) {
                 $title = '';
                       return $title;
                       }
                       add_filter( 'the_title', 'change_the_title', 10)

                       code for no title

                       With this, we hook into “the_title” with a function of our own called “change_the_title”. This accepts the variable $title which we simply set to nothing and return it. Just a few lines of code wipe out page titles across the site. Here’s what my post looks like as soon as I’ve implemented it:

                       title removed

                       But wait! What if I don’t want to remove titles across the site, but only on pages? Well then, the answer is simple. Simply include a check for a page before setting the title to an empty string. Our “change_the_title” function then becomes:

                       function change_the_title( $title) {
                            if (is_page()) {
                                      $title = '';
                                            }
                                                  return $title;
                                                  }

                                                  You can grant this even more flexibility by assigning those posts and pages for which you want to remove the title to a separate category or custom post type and then perform a check for that condition in the function.

### CSS Method
For this, I simply add the following CSS either to style.css or another theme independent location.

```
.entry-title {
     display: none;
     }
```

     change css

     And if you want to hide only the page titles, find out what unique class applies to that subsection of them. In my blog (and probably most of the others), the following code works just fine:

```
     .page .entry-title {
          display: none;
          }
```
