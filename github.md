# Github/Jekyll Blog Tutorial

## What even is GitHub/Jekyll?

GitHub is a code hosting platform for versioning (meaning keeping track of changes in code) and collaboration. But that's not what we'll be using it for. We'll be using Jekyll to create a static blog with no need for a hosting service, so it is free! 

You'll be using something called [Markdown](https://www.markdowntutorial.com/lesson/1/) to write your posts. It's really quite simple! It's not coding per se, but it does convert your styling to HTML for display on your website. It takes a little patience to learn the ins and outs of Markdown, but by the end of the semester, it will be second nature!

## Before you begin . . .

. . . you will need a GitHub account. If you don't have one yet, [sign up here](https://github.com/). Remember, when you're choosing your GitHub username, keep in mind FERPA (see the statement on the syllabus) and keep it professional and appropriate. Also, keep the name as simple as you can.

## Creating your site

GitHub uses *repositories* to organize projects. You'll be creating *one* repository for your project, since this will be a blog. There's a lot you can do with the repository features in GitHub, but we'll be keeping things pretty simple.

Go to [https://github.com/new](https://github.com/new) to make your blog repository. Simply type in your repository name under "Repository Name." Again, remember FERPA when choosing your name and keep it professional, appropriate, and simple. It can even be the same name as your GitHub username!

Note that you don't want to title the repository "About Me" or anything like that since we'll be writing several blogs over the course of the semester *within* this same repository. To be clear, all of your blog posts will be hosted within this single repository, so choose the name wisely. 

Make sure your blog is public so that we can all see it. 

![New Repository Gif](https://deanna-stover.github.io/coursesCNU/images/NewRepo.gif)

## Adding initial (and ESSENTIAL) content

To create your first file, go to your repository (this is the page you should be on if you just created your repository).

Under the heading “Quick setup — if you’ve done this kind of thing before,” there is a link called for “creating a new file”. Click on that.

On the resulting page, in the box captioned “Name your file,” type ```_config.yml``` (make sure to include the underscore at the start of the filename).

Copy and paste the following code block into the file editor (to the right of the number 1 and below “Edit new file”).

```
#
# This file contains configuration flags to customize your site
#
# Name of your site (displayed in the header)
title: Site Title
# Short bio or description (displayed in the header)
description: A Blog

#
# !! DON'T EDIT BELOW THIS MESSAGE
#
# Use the following plug-ins
plugins:
  - jekyll-sitemap # Create a sitemap using the official Jekyll sitemap gem
  - jekyll-feed # Create an Atom feed using the official Jekyll feed gem

# Exclude these files from your production _site
exclude:
  - Gemfile
  - Gemfile.lock
  - LICENSE
  - README.md
  - CNAME
```

In the editor, where the file says title: ```Site Title```, you can change “Site Title” to whatever you want your blog to be called. You can also edit ```description: A Blog``` to better describe your site. YAML is the file format used to configure your blog. (Note that I forgot to change the Site Title and Description in the GIF below, but you can always go back in and do this by clicking on ```_config.yml``` and then clicking the pen in the upper right hand corner--this allows you to edit any file you have committed.)

When you are done editing your file, scroll to the bottom of the page and click “Commit new file” to save your changes. “Commiting” is the fancy GitHub lingo for saving files to your repository (or repo).

![Creating new YAML file](https://deanna-stover.github.io/coursesCNU/images/YML.gif)

## Creating ```index.html``` file

Having created our first file, we need to create one more before we can start blogging. It’s going to be called ```index.html```. You can think of it as the front page of your new blog.

If you have learned HTML, the code we are copying may look a little strange. Jekyll, the blogging software used by GitHub Pages, uses some special code to turn our posts into HTML.

If you haven’t learned HTML yet, this all will probably look like a foreign language. But that’s ok, we’ll talk more about what all this does.

So on your repo, click on the “Add file” menu and select “Create new file” from the drop-down menu.

In the “Name your file” box, type “index.html”. In the file editor, paste the following code block:

```
---
layout: default
---
<div class="posts">
  {% for post in site.posts %}
    <article class="post">

      <h1><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></h1>

      <div class="entry">
        {{ post.excerpt }}
      </div>

      <a href="{{ site.baseurl }}{{ post.url }}" class="read-more">Read More</a>
    </article>
  {% endfor %}
</div>
```

Scroll to the bottom and click “Commit New File” to commit ```index.html``` to your repo.

![Creating index.html file](https://deanna-stover.github.io/coursesCNU/images/index.gif)


## Getting your blog up and running









