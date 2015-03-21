---
layout: post
title:  "CS Concepts (Coding): Find the largest int value in an int array."
date:   2015-03-21 20:35:18
categories: Coding
---

###[Steve Yegge Blog](https://sites.google.com/site/steveyegge2/five-essential-phone-screen-questions)
http://steve-yegge.blogspot.sg/2008/03/get-that-job-at-google.html

###Area Number One: Coding

{% highlight text %}
Example 6:  Find the largest int value in an int array.
{% endhighlight %}

{% highlight java %}
  int largestIntInArray(int a[]) {
    int len = a.length;
    int max = 0;
    if ((len & 1) != 0) {
      max = a[len - 1];
    }
    for (int i = 0, j = len - 1; i < len / 2; i++, j--) {
      if (max < a[i]) {
        max = a[i];
      }
      if (max < a[j]) {
        max = a[j];
      }
    }
    return max;
  }
{% endhighlight %}
