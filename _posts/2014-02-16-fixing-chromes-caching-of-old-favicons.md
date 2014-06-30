---
layout: post
title: "Fixing Chrome's caching of old favicons"
description:
category: blog
tags: [chrome, jekyll, blog, sqlite]
comments: false
image:
  background: witewall_3.png
share: true
---

For the past 2-3 days I've been wrangling with updating the favicon for my blog.
I've built this blog using Jekyll, and running

    {% highlight bash %}
    jekyll serve --watch
    {% endhighlight %}

builds the site and watches for changes.
A quick switch over to Chrome, and BOOM! your latest content is up and running on 

    {% highlight bash %}
    localhost:4000
    {% endhighlight %}

But after changing my `favicon.ico`, my favicon would not display correctly.
So here starts the bug-hunting.

1. Force refresh? _nope._
2. Clearing browser cache? _nope._
3. Restart Chrome? _nope._
4. Check favicon loads on Safari/Firefox? _yup._
5. Think Chrome sucks at this point? _maybe. It's still undeniably fast :P_
6. Double check git logs for pushing the right favicon? _yup._
7. Downloading the raw file from master repo to double check? _yup._
8. Emailing Github support to check if the CDN is not doing its job? _nope. It's just me apparently. (btw Github support is super duper fast, cheers to them!)_
9. Googling for `chrome favicon cache`, best result found [here](https://productforums.google.com/forum/#!topic/chrome/zXlEW0ZFErY)? _seems legit. It's really sad this issue hasn't been resolved since 2011._
10. Instead of blindly following forum posted advice (~shudder~) of deleting the sqlite3 db file:

    {% highlight bash %}
    ~/Library/Application\ Support/Google/Chrome/Default/Favicons
    {% endhighlight %}
* Going to be a db ninja and open it up myself with
    
    {% highlight bash %}
    sqlite3 ~/Library/Application\ Support/Google/Chrome/Default/Favicons
    {% endhighlight %}

* Find the suspect entry

    {% highlight sql %}
    select * from favicons where url = 'http://www.calvintam.me/favicon.ico'
    {% endhighlight %}

* Remove the suspect entry

    {% highlight sql %}
    delete from favicons where url = 'http://www.calvintam.me/favicon.ico'
    {% endhighlight %}
    
* Refresh Chrome
* Voila! Problem solved.

_PS: There were many different solutions for forcing the refresh of the favicon, such as [this post](http://stackoverflow.com/questions/2208933/how-do-i-force-a-favicon-refresh) on StackOverflow. The proposed solutions were quite varied but really resolved the issues on different parts/level of the web stack. This appeared more of a Chrome-specific local issue, so this seemed the cleanest solution._
