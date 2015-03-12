---
layout: post
title: "Ember.js: A first impression"
category: blog
modified: 2015-03-12 10:11:47 -0700
tags: [ember, javascript, learning, framework]
comments: false
share: true
site_section: Blog
---

Ember. A framework for creating ambitious web applications. Is it worth investing in? Does it suit your needs?

Those were the main thoughts that ebbed and flowed as I plowed through the plethora of Javascript frameworks out there and continued well into the time I had already committed to using it.

In short, Ember is powerful and all-encompassing. Do it "The Ember Way™" or you'll find yourself a hard time.

The typical trio that is quoted as the 'top 3 Javascript frameworks' are in 2015: 1) BackboneJS, 2) AngularJS, and 3) Ember.js. Having worked in production on Backbone and Ember, and a teeny tiny bit on Angular on a previous side project, it is clear even from beginners that the aforementioned list is increasing in orders of complexity and hence their learning curves.

So back to how it all started: there was a data-intensive internal tool that needed to be built to automate a lot of the existing manual data pulling, wrangling, sharing, updating for scheduling multi-market sales. For far too long these manual processes were reliant on non-tech savvy business people who would manually copy-paste data and share them via emails. Life was rather miserable, and this tool would be their godsend.

Fast forward to decision time on which Javascript framework to pick for this app, it was clear that Ember was a smart choice after prototyping a subset of the app but not without it's gripes. Here are the reasons:

* **Complex data management** – The app does not perform simple CRUD operations, it needs to keep track of user inputted data, and the associated changes that result from the user's interaction (e.g. reordering table rows, add/remove data but keep track of it until it has been confirmed by user). Managing this using plain ol' jQuery would be reinventing the wheel, so data plugins of any of the js frameworks would be a good start. Ember has Ember-Data which does a decent job on the most use cases but unless your app is similar to Ember-Data's mindset, you'll end up fighting it more often than not. In my case, Ember-Data got me 80% of the way, and the rest were either overriding defaults or implementing my own custom adapters. The Ember ecosystem is highly opinionated and there were many a time where it almost seemed like an uphill battle just to get Ember-Data to work.

* **Build and deployment tools** – As an internal app, there is a lot of freedom in technology stack but it is always wise to stick to open source work that has a strong community backing and a plentiful set of tooling. In my case, ember-cli was exactly what was needed: a command line tool that gave community-defined standard app structure, good default one-command build/deploy tools to get going, and extensibility with community add-ons. Main gripes? ember-cli is still a work-in-progress. Documentation is rather lacking. Breaking changes. 

* **Complex User Interactions** – The main factors to complex data management is because of the 1) problem domain and 2) user interaction. From the standpoint of the end user, this app is meant to give them the power to manipulate the underlying data to the problem domain. They expect fast and responsive interactions that model their perception of what is going on. Ember's monolithic architecture means if you stick to "The Ember Way™" all is taken care of. In this case, Ember has a managed and well-defined queueing model called the Ember run loop. A part of its job is to manage the re-rendering of views based on changes in the underlying data and also from user interaction. This two-way binding really makes Ember shine.

* **Testing** – The app has a data dependency to a backend API while also dealing with lots of user interaction. Ember has a version of QUnit built into it which makes testing **part of the framework**. Again sticking to the Ember way or the Ember defaults, meant I could write intergration tests from day one which from a business perspective is key since it drives the behavioural flow of the development process. Ultimately, sticking to defaults save time re-wiring the same things across projects.

* **Community Support** – Last but not least, being a complete fresher to Ember I needed to know I had the backing of the community. What I mean is a vault of knowledge from my predecessors who have asked questions that are easily searchable on StackOverflow for really specific, common problems/bugs and a momentum in the influx of community plug-ins and add-ons. There has been countless times where there are strange error messages that just don't make sense. A quick google search of keywords and BOOM we're done.

Having given the context of the application of Ember, it was obvious that the learning curve for Ember was a crazily steep one since Ember manages everything for you. Every last detail. If I were to give advice to my old self, I would definitely say _"spend a good full week learning The Ember Way™ first before you write any Ember code"_. The reason I say this is because too many times did I fall into the trap of trying to fight Ember and doing things my way when it was just a missing piece of prior knowledge. Another piece of advice is that Ember does not play well with other frameworks. Trying to incorporate jQuery Sortable UI plugin into Ember was a nightmare because the plugin has its own view of its scope in manipulating DOM elements but this conflicts with Ember who also manages the view that encompasses those DOM elements as it re-renders bases on its internally managed models.

Learning and working with Ember has been a hair-pulling experience that to its credit has stood up to its motto of building ambitious web applications... The Ember Way™.
