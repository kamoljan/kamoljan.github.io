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
  long sumIntsFromFile(String fileName) {
    long sum = 0;
    BufferedReader br = null;
    try {
      String line;
      br = new BufferedReader(new FileReader(fileName));
      while ((line = br.readLine()) != null) {
        try {
          sum = sum + Integer.valueOf(line);
        } catch (NumberFormatException e) {
          e.printStackTrace();
          return -1;
        }
      }
    } catch (IOException e) {
      e.printStackTrace();
      return -1;
    } finally {
      if (br != null) {
        try {
          br.close();
        } catch (IOException e) {
          e.printStackTrace();
        }
      }
    }
    return sum;
  }
{% endhighlight %}

{% include cs_copyright.html %}