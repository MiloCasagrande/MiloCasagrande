---
author: milocasagrande
comments: true
date: 2015-03-08 08:01:15+00:00
layout: post
link: https://www.milo.name/2015/03/08/make-nginx-return-a-json-response/
slug: make-nginx-return-a-json-response
title: Make nginx Return a JSON Response
wordpress_id: 569
categories:
- Development
tags:
- development
- server
- web
---

_This is more of a "write here so I do not forget" kind of post._

I set out trying to make a simple "maintenance" mode for a [REST](https://en.wikipedia.org/wiki/Representational_state_transfer) API (that speaks only JSON) without having to handle it in the code base.

[nginx](http://nginx.org/) has a really cool support for maintenance mode that is dead easy to set up:

    if (-f $document_root/maintenance.html) {
        return 503;
    }

Obviously, life is not that easy.
In my case, the same URL is used to show static content (the API docs) and only sub-dirs in the URL are used for the API resources:

    api.example.net
    api.example.net/resource1
    api.example.net/resource2
    
I already handle the API resource definitions in nginx, and I only need to override the root maintenance definition. In addition, the JSON response should also have the correct Content-Type header set.

In this case, is probably "easier done than said", and is all done in here:

    if (-f $document_root/maintenance.html) {
      more_set_headers "Content-Type: application/json; charset=UTF-8";
      return 503 '{"code": 503, "reason": "Service maintenance."}';
    }

The trick is in having the _[nginx_headers_more](http://wiki.nginx.org/HttpHeadersMoreModule)_ module enabled and installed in your system.

On a Debian based distribution, the module is in the _nginx-extras_ package.
