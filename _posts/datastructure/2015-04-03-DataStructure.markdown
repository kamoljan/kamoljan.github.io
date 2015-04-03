---
layout: post
title:  "Data Structure"
date:   2015-04-03 14:35:18
categories: Data Structure
---

#### Stacks
{% highlight java %}
  public void stackIsLifo() {
    Stack stack = new Stack();
    stack.push("1");
    stack.push("2");
    stack.push("3");

    System.out.println(stack.pop() + " is gone!");
    System.out.println("What left is " + stack);
  }
{% endhighlight %}

Result
{% highlight test %}
3 is gone!
What left is [1, 2]
{% endhighlight %}

#### Queue
{% highlight java %}
  public void queueIsFifo() {
    Queue<Integer> queue = new LinkedList<Integer>();
    queue.add(1);
    queue.add(2);
    queue.add(3);

    System.out.println(queue.remove());
    System.out.println(queue);
  }
{% endhighlight %}

Result
{% highlight test %}
1
[2, 3]
{% endhighlight %}

