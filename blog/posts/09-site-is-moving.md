---
title: "[NOTICE] Site Is Moving, and Things Will Break"
author: Tzu-ping Chung
published_at: 2017-01-09
---

TL;DR: I am making the site static, and some things will break. **You should update your subscription feed if you’re subscribed to the blog.**

----

We are moving.

The official site of MacDown has been a Django project that runs on the Heroku free tier. I liked the solution at the time, but gradually it became clear that it is an overkill to maintain a fully-functional web app as a landing page.

Hosting is also a problem; Heroku offers only 512 MB for free dynos, meaning that the site goes down pretty easily with heavy traffic—which does not happen often (the site currently gets about 700 visitors a day), but it still [happened](https://github.com/MacDownApp/macdown/issues/504) a couple of times. HTTPS is unavailable with custom domain, and the 30-minute auto-sleep feature is also annoying. I’m not saying Heroku is bad—it is an excellent service, just not suitable for this particular use case.

The more I thought about this, it became clearer I really should implement this as a static site. Most of the things are already static, and those that are not can become static with a bit of work. The tipping point came when the always wonderful [Armin Ronacher](http://lucumr.pocoo.org/about/) published his home-baked static site generator, [Lektor](https://www.getlektor.com). And so I went to work.

You can see a preview of the new site at <https://macdownapp.github.io>. It stills lacks some critically parts, and will likely require some time before begin fully ready, but I am confident it will work.

**But there’s a catch.** Lektor is still in its early stages, and there are some things on Django I can’t replicate on it. Two of these could be very significant for you, reading this post:

1. **Atom subscription URL will change.** You need to change the URL to `macdown.uranusjr.com/blog/feed/atom.xml` instead. I added the new route to the current site, so you can do this right now, and everything will work after the migration.
2. **RSS 2.0.1rev2 subscription will be dropped.** If you’re subscribed to the RSS feed, you will need to switch to Atom at `macdown.uranusjr.com/blog/feed/atom.xml`.

Here’s to the migration went smoothly. Hopefully I will see you soon on the new site.