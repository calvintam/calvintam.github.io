---
layout: post
title: "Code golf with Python"
description:
category: blog
tags: [programming, python]
comments: false
image:
  background: witewall_3.png
share: true
---

Recently been practising programming interview questions with Python, which has been a lot more fun than when I was using Java.

The typical question that has been done to death is the "*Reverse Words in String*" question, which is best demonstrated in a few examples:

{% highlight python %}
Simple case
Input: "Hello world, I am a computer"
Output: "computer a am I world, Hello"

Multiple space case
Input: "  Some leading space, and no trailing space"
Output: "space trailing no and space, leading Some  "
{% endhighlight %}

Sure there's the optimized solution that every interviewer is after - [Hacking a Google Interview](http://courses.csail.mit.edu/iap/interview/Hacking_a_Google_Interview_Handout_2.pdf) - but it's a lot more fun to do a code golf solution:

{% highlight python linenos=table %}
    def reverse_string(string):
        return ' '.join(string.split(' ')[::-1])
{% endhighlight %}

Step-by-step explanation (by order of evaluation):

{% highlight python %}
    string.split(' ')
{% endhighlight %}

Question typically asks for the delimiter to be the space character (if the interviewer is really keen on different whitespace characters, then just use Python's `re` module and split on `\s`), so the string's builtin `split` function will just return an array of strings (can be empty) that were found in between such spaces.

{% highlight python %}
    string.split(' ')[::-1]
{% endhighlight %}

Since the `split` function produced an array, we can now move the tokenized words in the string. Python allows you to specify the iteration step when iterating via indices, the format being `[start_index (included) : end_index (excluded) : iteration_step]`. The way we've opted to use it, is to not specify the start or end indices and providing a negative iteration step which essentially iterates in the reverse direction. This produces a reversed copy of the array.

{% highlight python %}
    ' '.join(string.split(' ')[::-1])
{% endhighlight %}

Once we have the reversed array of words in place, all we need to do is to join them back with spaces into a string and hey presto!

Yet another example demonstrating the elegance of Python  :)
