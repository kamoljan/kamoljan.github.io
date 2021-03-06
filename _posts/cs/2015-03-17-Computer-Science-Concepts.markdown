---
layout: post
title:  "CS Concepts (Coding): Write function to compute Nth fibonacci number"
date:   2015-03-17 14:35:18
categories: Coding
---

#### Example 2: Write function to compute Nth fibonacci number.
{% highlight text %}
Input:  1, 2, 3, 4, 5
        |  |  |  |  |
        v  v  v  v  v
Output: 0, 1, 1, 2, 3
{% endhighlight %}

{% highlight java %}
  static int fib(int n) {
    int a = 0, b = 1, c = 0;
    if ((n <= 0) || (n >= Integer.MAX_VALUE)) {
      return -1;
    } else if (n == 1) {
      return 0;
    } else if (n == 2) {
      return 1;
    } else {
      for (int i = 2; i < n; i++) {
        c = a + b;
        a = b;
        b = c;
      }
    }
    return c;
  }
{% endhighlight %}

#### Steve Yegge Java and C/C++ solutions

{% highlight java %}
  static long fib(int n) {
    return n <= 1 ? n : fib(n-1) + fib(n-2);
  }
  // (Java Test harness)
  public static void main ( String[] args ) {
    for ( int i = 0; i < 10; i++ ) {
      System.out.print ( fib(i) + ", " );
    }
    System.out.println ( fib(10) );
  }
  // (C/C++ Test Harness)
  main () {
    for ( int i = 0; i < 10; i++ ) {
      printf ( "%d, ", fib(i) );
    }
    printf ( "%d\n", fib(10) );
  }
{% endhighlight %}

{% include cs_copyright.html %}
