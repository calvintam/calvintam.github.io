---
layout: post
title: "Adventures in AngularJS"
category: blog
modified: 2014-05-22 22:09:23 +1000
tags: [angularjs, javascript, programming, web]
image:
  background: witewall_3.png
  feature: 
  credit: 
  creditlink: 
comments: false
share: true
angularjs_logo_url: "/images/angularjs-large.png"
site_section: Blog
---
<figure style="text-align: center;">
  <img src="{{ page.angularjs_logo_url }}" />
</figure>

It typically takes me 2-3 attempts at learning a programming language or framework before the productivity boost really kicks in.
I find that moving across different mediums and sources are far better than sticking with the 'best and most highly recommended' book.
Screencasts, live demos, ebooks, and articles are all good resources.

My next endeavour is to learn and play with the major JavaScript frameworks: AngularJS, Ember.js, and Backbone.js.
I previously had a crack at Ember and Backbone via Codeschool, but unfortunately the course for Angular had not been developed then.
My initial impression of Ember was just as their same motto said: "for building ambitious applications".
It definitely seemed like quite a steep learning curve but it was evident that following the "Ember" way ensured that larger-scale applications would not turn into a pile of spaghetti code.
Though for personal fun projects, this was definitely overkill.
Backbone on the other hand was 'closer to the metal', and was highly configurable, tailorable to the developer's needs.
However, this also meant it again was a lot of lines of code just to accomplish even the simplest of things.

So after letting these experiences simmer for a while, Angular popped up on my Twitter feed linking back to [this Youtube video](https://www.youtube.com/watch?v=HCR7i5F5L8c) on the design decisions behind Angular and after watching it, there were lots of features/design decisions which really resonated.
Things that I can think of on top of my head having tried it out for an in-the-making webapp:

* **Declarative code** - unlike Backbone which is rather bloated because the code that manipulates the UI elements are very procedural, and brittle when meshed with the presentation layer. Angular on the other hand uses directives that encapsulate this logic and allows the attachment of declarative hooks that abstracts the complexity. Another nice feature is filtering - e.g. `{{ "{{ 1234 | number:2 " }}}}` means 'send 1234 to the filter `number` with arguments `2`, which represents the number with 2 decimal places'. The use of the `|` (pipe) symbol which mimics shell pipelining is both intuitive and makes the UI interactions more modularised and composable.
* **Modularisation** - the structure of an Angular is incredible modular. This was a design decision right from the start to make it testable and easy to work with. Want a modular service/factory for a JSON REST API? Sure just create it with `yo angular:factory FactoryName` (I use Yeoman for my AngularJS apps) and your service/factory is in its own js file and comes with accompanying stub tests!
* **Dependency Injection** - for my bitcoin currency converter app, I needed to pull JSON data from an exchange feed API. Typically in Backbone, this would usually rely on jQuery's ajax facilities, but in Angular we just need to add a dependency to `ngResource` and reference the `$resource` utility which allows us in one line to wrap the JSON provider as a RESTful resource. The cool thing is that Angular was able to resolve this dependency for me implicitly without all the fluff of redeclaring the module somewhere else. Staying DRY is great!
* **Two-way data-binding** - perhaps the coolest of features in Angular is how data represented in the DOM is updated with the model behind-the-scenes. This is particularly useful for responsive client-side web apps as it saves the user having to click the submit button everytime just to see an update, and also ensuring data integrity, as the Angular team would say "keeping a single source of truth - in the DOM". I've been using this feature in my bitcoin converter app, allowing clients to type in any amount and see live changes to the valuation.

I'm sure there are lots more cool (and ugly) things about Angular that I'll learn while building client-side apps with it, but once I've gotten familiar with Angular, it'll be very interesting to dive into Ember and really see first-hand the pros and cons of each.
