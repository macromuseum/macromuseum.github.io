## Help with the blog
### Adding a blog post
* In `macromuseum.github.io/_posts` create a `.md` file named as follow:
  * year-month-day (e.g. 2015-1-1 or 1212-12-12)
  * your-blog-name (e.g. how-to-add-a-blog)
  * The result should look like `2015-1-1-how-to-add-a-blog.md`
* Make sure to add the right header to your post:
```
---
layout: post
title: The title of my blog post (It C0uLD b3 @nyTHING!)
---
```
* Then write your blog post in Markdown. If you need to add images, you can add the in `macromuseum.github.io/images` and embed them as `![_config.yml]({{ site.baseurl }}/images/YourNicePicture.jpg)`
* Finally, just sync your repo and push your new blog post. It'll magically appear!

#### Images:
There are (for now) three ways to add images to you post.

##### Normal (in text) image
This is the easiest way to embed images, they'll just appear unformatted as you called them along the text or as a new image (if it's a big image, it'll be big).
````
![_config.yml]({{ site.baseurl }}/images/YourNicePicture.jpg)
````

##### Header image
This one is to add a header image to your post (recommended). The image will appear on the blog main page (like a graphical abstract). This can be done easily by adding the following just after the header:
````
 
![headimg]({{ site.baseurl }}/images/YourNicePicture.jpg)

````
Note that the two empty lines (before and after) are essential. You can also add some text like an catchy sentence as follow (same, empty lines are important).
````
 
![headimg]({{ site.baseurl }}/images/YourNicePicture.jpg)
This is a really catchy sentence, I can't wait to read the rest!
 
````

##### Resized image
An other way to add pretty picture is to have automatic resized and centered pictures (so all your pictures have the same layout). That's also easy, just use the following:
````
![bodyimg]({{ site.baseurl }}/images/YourNicePicture_WhateverSize.jpg)
````
This will automatically center your image and set the height to 200px (without transforming the ratio). You can also add a fancy quote to the image like this:
````
![bodyimg]({{ site.baseurl }}/images/YourNicePicture_WhateverSize.jpg)
<center>My quote</center>
````
Note the <center> tags. You can also add a mouse over text as follows:
````
![bodyimg]({{ site.baseurl }}/images/YourNicePicture_WhateverSize.jpg "Some mouseover text")
<center>My quote</center>
````
Note the straight quotations marks - essential! Finaly, you can also add a link to your picture with the original dimensions as follows:
````
[![bodyimg]({{ site.baseurl }}/images/YourNicePicture_WhateverSize.jpg) "Some mouseover text" ]({{ site.baseurl }}/images/YourNicePicture_WhateverSize.jpg)
<center>My quote</center>
````
So that when you click on the picture it gives you the full sized one (handy for phylogenies!).

### Other tips
##### Draft posts:
You want to draft your post before sending it to the whole world? Super easy: instead of writing the date at the start of your markdown file, just write anything (like `Someday-My-post.md`). Then just replace `Someday` by the actual date and pouf! it'll be posted.
### Creating new pages in the upper bar menu (WARNING: can break the internet)
It's possible to add pages to the menu (i.e. "About", "How to post") this way:
* duplicate one of the *menu* folder (such as "about" or "howto") in `BESMacro.github.io/_site`
* add a `.md` file in the root (`BESMacro.github.io/`) with the same name as the *menu* folder
* be sure the start the `.md` file with the right header
```
---
layout: page
title: The title of the new page
permalink: /<menu_folder>/
---
```
* then add the page to the [default template](https://github.com/BESMacro/BESMacro.github.io/blob/master/_layouts/default.html) in the `<body><nav>`:

````
<...>
   <nav>
      <a href="{{ site.baseurl }}/">Blog</a>
      <a href="{{ site.baseurl }}/about">About</a>
      <a href="{{ site.baseurl }}/howto">How to post</a>
      <a href="{{ site.baseurl }}/legal">Legal Mumbo Jumbo</a>
      <a href="{{ site.baseurl }}/your_new_page">The page name</a>
   </nav>
<...>
````
Note that the order of where the page is in the `<nav>` will be where the link to the page will actually appear.

* finaly build the website using (be sure you installed [all the dependencies](https://help.github.com/articles/using-jekyll-with-pages/)):
```
 bundle exec jekyll serve
```

### Changing some design features (WARNING: can break the internet - big time!)
* `_config.yml` is the yamal file that contains easy fixable details for the whole website (title, description, bottom bar buttons, etc..)
* `_layout/` contains the templates for the layout (e.g. blog posts, main page, etc...)
* `_sass/` contains the scss files (namely `_variables.scss` that you should use to set the template variables)
* `style.scss` is the Jekyll *css-like* file  (if you wanna break some things, that's the place to go!)
The savest way to play with these is to do it on your internal server using `bundle exec jekyll serve`. Note however for changes in the yamal file you have to refresh the localhost each time. If you're happy with your messing up, just sync the repo and push!
