---
layout: post
title:  "CS Concepts (Coding): Write a function that sums up integers from a text file, one int per line."
date:   2015-03-21 14:35:18
categories: Coding
---

{% highlight text %}
Example 1:   Write a function that sums up integers from a text file, one int per line.
{% endhighlight %}

{% highlight java %}
  void printOdds(int a, int b) {
    int oddStart;
    // oddStart = a % 2 == 0 ? a + 1 : a;
    oddStart = (a & 1) == 0 ? a + 1 : a;
    for (int i = oddStart; i <= b; i += 2) {
      System.out.print(i + " ");
    }
  }

{% endhighlight %}

{% include cs_copyright.html %}