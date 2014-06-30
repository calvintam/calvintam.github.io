---
layout: post
title: "The power of XOR for data recovery"
description:
category: blog
tags: [google, internet, data, software]
comments: false
image:
  background: witewall_3.png
share: true
site_section: Blog
---

Reading the High Scalability blog post - "[_How Google Backs Up The Internet Along With Exabytes Of Other Data_](http://highscalability.com/blog/2014/2/3/how-google-backs-up-the-internet-along-with-exabytes-of-othe.html)" - I came across this simple, somewhat fundamental, trick which were of the many tactics used to ensure no data loss:

> "_Build up 4 full tapes and then generate a 5th code tape by XORing everything together. You can lose any one of the 5 tapes and recover the data._"

The key thing to note is that you can lose **any** of those tapes and still be able to reproduce that lost one so long you have the rest of the tapes available.
The backup tape is essentially the resulting 'checksum' that doesn't just hint at data loss/corruption, but can be used to actually rectify the issue.

The main saving that comes out of this technique is that you do not need to backup **each** tape, reducing redundancy by a large factor.

However the trade-off that needs to be considered is the number of original tapes that backup tape is responsible for.
In Google's case, they need a 100% guarantee that the data will never be lost, so a 4:1 ratio seems reasonable in terms of price and security.

This is a real-life application of XOR for finding missing data, encapsulated in this typical programming interview "_[Find the missing element between two arrays](http://www.ardendertat.com/2011/09/27/programming-interview-questions-4-find-missing-element/)_". Always a good thing to be able to relate programming interview questions with an actual use case, rather than some esoteric, non-useful problem.

