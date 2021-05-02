---
layout: post
title: How to use allejo's jekyll-toc using CSS
author: Bryan
categories: webdev 
---
I support this website using a combination of jekyll and github pages. Unfortunately, github restricts a immense ammount of plugins so a lot of work arounds have to be found in order to make seamingly simple tasks work. This has lead to my use of [allejo's excellent table of contents snippet](https://github.com/allejo/jekyll-toc). However, I find the documentation isnt exactly intuitive and for someone who isnt used to the world of webdev can be come confusing. My hope is to show you how to implement allejo's toc and how to apply CSS to it. 

## Implementing The T.O.C.
If you want a simple working table of contents, simply put `{% raw %}{% include toc.html html=content %}{% endraw %}` in the same HTML layout where you have  your `{% raw %}{{ content }}{% endraw %}`. However, if you want to customize your table of contents you need to add a few more parameters to the above liquid function call. This is shown within the `toc.html` file where they show an example of what you need.

{% highlight md linenos %}
    {% raw %}
        {% include toc.html html=content sanitize=true class="inline_toc" id="my_toc" h_min=2 h_max=3 %}
    {% endraw %} 
{% endhighlight %}

the class and id variables can be tailored to whatever you want to call them. From here we can begin styling our table of contents. 

## Styling The Table Of Contents
There are a couple of components to understand when styling your table of contents. 
* `<ul></ul>` In your css call the `ul` tag when wanting to apply CSS to the entire unordered list
* `<li></li>` In your css call the `li` tag when wanting to apply CSS to specific list items
* `<a></a>` In you css call the `a` tag when wanting to apply CSS to specific text corresponding to the linked item. 

#### Example
For reference this is how my CSS looks to achieve the table of contents as of 5/2/2021

{% highlight html linenos %}
    .the_toc ul{
        font-size: 100%;
        color: var(--text);
        list-style-type: none;
        text-decoration: none;
        position: sticky;
    }

    .the_toc li{
        font-size: 90%;
        color: var(--text);
        list-style-type: none;
        margin:0 0 10px 0;
        top: 2em;
    }

    .the_toc a{
        color: var(--text);
        text-decoration: none;
    }
{% endhighlight %}

I hope this helps.

## Comments Section
If it doesnt help, I was overly vague, or you need assistance please do not shy away from commenting below.
