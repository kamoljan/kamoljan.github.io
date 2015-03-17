---
layout: post
title:  "Computer Science Concepts"
date:   2015-03-17 14:35:18
categories: Coding
---

###[Steve Yegge Blog](https://sites.google.com/site/steveyegge2/five-essential-phone-screen-questions)

###Area Number One: Coding

{% highlight java %}
Example 2:  Write function to compute Nth fibonacci number.
Input:  1, 2, 3, 4, 5
        |  |  |  |  |
        v  v  v  v  v
Output: 0, 1, 1, 2, 3

{% endhighlight %}

{% highlight java %}
  static String fib(int n) {
    int r = 0;
    int a = 0, b = 1, c;
    if (n <= 0) {
      return "The N should be equal or greater than 1";
    } else if (n == 1) {
      return "0";
    } else {
      for (int i = 0; i < n; i++) {
        if (i == 0 || i == 1) {
          r = i;
        } else {
          c = a + b;
          a = b;
          b = c;
          r = c;
        }
      }
    }
    return "" + r;
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