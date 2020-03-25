---
title: My Cheap Server Journey
date: 2020-03-25
---

# My Cheap Server Journey

_TL;DR I was using Heroku then cheap VPS's but I wanted to see if I could get my monthly costs down to $0 and I did._

Let's start with what the goal is here. The goal is to run several high touch (in terms of customer acquisition/support), low traffic SaaS apps (read: expensive), possibly 10-20 apps all said and done, all self service with sales and support by yours truly.

I started out with a git push to heroku and everything just worked™️. I wanted to host quite a few apps though and $7/mo per app is a steep price to pay when you aren't making any money. So I started looking at how to reduce my costs.

I started by switching away from heroku to a $5/mo VPS but after seeing how much memory rails uses, I wasn't going to be able to run too many rails apps on one server. So I increased it to $10/mo. Luckily I was getting indoctrinated into the ultimate solo programmer programming language: lisp, after that I started writing all of my useless side projects in clojure specifically and it reduced the memory usage quite a bit to boot!

$10/mo when there's no money coming in is a drag. So I started looking for alternatives to my clojure stack and I found JAMStack. It's a nice sentiment, your stuff is static, everyone else's is dynamic. Hosting on netlify or now or render is free for static sites! Just what I was looking for. Of course, if you want a few forms here and there or some analytics, you're going to have to depend on an API for that: the A in JAM. You're also going to want to write a bunch of javascript for interactivity, the J in JAM. The complexity skyrockets if you want something that behaves like a traditional three-tier app on the JAMStack.

That was a no go. It's perfect for sites with a few forms though or landing pages.

I've talked about this already but enter Janet, it's a clojure-syntax inspired lisp that starts super quick and requires barely any memory thanks to it's C roots. Nice. I reduced my monthly spend to about $3.50/mo with a vultr VPS but I decided it still wasn't good enough. For this next bit I had to go way back, back before PaaS, before the cloud, before virtual private servers. I also had to go into the future with cloudflare, a raspberry pi and dynamic dns. I would like to rely on ipv6 at some point and not cloudflare/dynamic DNS but I live in an ipv4 world, so there it is.

After a $35 raspberry pi, $0 on cloudflare, a hole punched in my router for incoming port 80 and 443 connections, and an open source bash script running in cron on that same raspberry pi, I have finally done it. I've opened myself up to a huge security risk BUT at the same time, I now pay $0/mo to host my janet side projects on a raspberry pi in my closet, just like the internet was always meant to be.
