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
Example output: 0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55
{% endhighlight %}

{% highlight java %}
  static void fib(int n) {
    int a = 0, b = 1, c;
    for (int i = 0; i <= n; i++) {
      if (i == 0 || i == 1) {
        if (i != 0) {
          System.out.print(", ");
        }
        System.out.print(i);
      } else {
        c = a + b;
        System.out.print(", " + c);
        a = b;
        b = c;
      }
    }
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