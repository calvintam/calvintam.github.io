---
layout: post
title: "Preloading with the newly built-in Spring on Rails 4.1"
description:
category: blog
tags: [rails, software engineering, project]
comments: false
image:
  background: witewall_3.png
share: true
site_section: Blog
---

For a new side project that I have started recently, I decided to move from Rails 3.2 over to Rails 4.1 (rc2 as of today) to see what new features have been put in place.
One particular feature that struck me was the integration of the Spring preloader into the core Rails code, which was a separate gem back in Rails 3.X and was qutie fiddly to setup initially.

The feature branch can be found on [Github](https://github.com/rails/rails/pull/12958).

The Spring gem preloads the application, and as per the [official README](https://github.com/rails/spring#readme): '*speeds up development by keeping your application running in the background*'. 
This is an amazing feature during the development process as it reduces the waiting time for running tests or a database migration.

Following the Rails philosophy, good practices or repetitive things should be automated, and Spring definitely are one of those small things that add up to a smoother development workflow.
