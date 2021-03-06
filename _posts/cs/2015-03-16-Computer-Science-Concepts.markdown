---
layout: post
title:  "CS Concepts (Coding): Write a function to reverse a string"
date:   2015-03-16 14:35:18
categories: Coding
---

#### Example 1:   Write a function to reverse a string
{% highlight java %}
Example output for "Madam, I'm Adam":   madA m'I ,madaM
{% endhighlight %}

{% highlight java %}
  private static String myReverse(String str) {
    String out = "";
    int length = str.length();
    for (int i = 1; i <= length; i++) {
      out = out + str.charAt(length - i);
    }
    return out;
  }

  // Faster one (the same as Steve Yegge's one)
  private static String myReversFaster(String str) {
    int length = str.length(), last = length - 1;
    char[] chars = str.toCharArray();
    for (int i = 0; i < length / 2; i++) {
      // first half
      char c = chars[i];
      chars[i] = chars[last - i];
      // second half opposite
      chars[last - i] = c;
    }
    return new String(chars);
  }

  // Another alternative with StringBuilder
  public static String SwamiReverse(StringBuilder str) {
    //return str.reverse().toString();
    for (int i = 0, j = str.length()-1; i < str.length()/2; i++, j--) {
      char c = str.charAt(i);
      str.setCharAt(i, str.charAt(j));
      str.setCharAt(j, c);
    }
    return str.toString();
  }
{% endhighlight %}

{% include cs_copyright.html %}