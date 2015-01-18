---
layout: post
title: "Nginx as a Proxy Server"
category: blog
modified: 2015-01-17 20:38:17 -0800
tags: [nginx, backend, server]
comments: false
share: true
site_section: Blog
---
For an upcoming company hackathon I was fiddling around with an open source project that produced amazing social network graph visualizations, and wanted to incorporate existing company-wide front-end assets to transform it into a new internal tool.

We already had a layout service serve these css, fonts and image assets in a CDN-like manner and all that was required was to link back to this server.

The only problem is that for an app running under `localhost`, the browser will promptly deny such cross-origin http requests (CORS) since it either doesn't match the allowed domains or there's no `Access-Control-Allow-Origin` header being set.

To get around this restriction, it's common to use a proxy server such as `nginx` to funnel requests to such assets without hitting the CORS block.

Accomplishing this is simple, just a quick addition to the `nginx.conf` file (which can be found in a variety of places, typically `/usr/local/etc/nginx/nginx.conf`):

  {% highlight bash %}
  ...

  http {
    ...

    listen 8100;                         ## The port you will be hitting to reach the nginx proxy server
    server_name localhost;               ## How you want your server to be displayed in the browser address bar

    location /layout/ {                  ## Capture all /layout/* requests and funnel them to the staging server which has the required assets
      proxy_pass http://staging.example.com/layout/;
    }

    location / {                         ## Redirect all other requests to the local running dev server for your app
      proxy_pass http://localhost:8000;  ## The port number is just whatever your dev server runs on
    }

    ...
  }
  {% endhighlight %}

Then either start your nginx server (`nginx`) or just reload it (`nginx -s reload`).

Happy hacking!
