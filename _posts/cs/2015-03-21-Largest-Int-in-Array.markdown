---
layout: post
title:  "CS Concepts (Coding): Find the largest int value in an int array."
date:   2015-03-21 20:35:18
categories: Coding
---

#### Example 6:  Find the largest int value in an int array.

{% highlight java %}

  // 31378000-39787000
  int largestIntInArrayFaster(int a[]) {
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

  // 34542000-51291000
  int largestIntInArray(int[] a) {
    int max = a[0];
    for (int i = 1; i < a.length; i++) {
      if (max < a[i]) {
        max = a[i];
      }
    }
    return max;
  }

{% endhighlight %}

### Test

{% highlight java %}
  int b[] = new int[100000000];

  @Before public void setUp() throws Exception {
    myClass = new MyClass();
    Random random = new Random();
    for (int i = 0; i < b.length; i++) {
      b[i] = random.nextInt();
    }
  }

  // 962296 vs 962304
  @Test public void memoryConsumption() {
    System.out.println("================== MEMORY ========================");
    System.out.println(myClass.largestIntInArrayFaster(b));
    // Get the Java runtime
    Runtime runtime = Runtime.getRuntime();
    // Run the garbage collector
    runtime.gc();
    // Calculate the used memory
    long memory = runtime.totalMemory() - runtime.freeMemory();
    System.out.println("Used memory is bytes: " + memory);
    System.out.println("==================================================");
  }

  // 31378000-39787000 vs 34542000-51291000
  @Test public void timeConsumption() {
    System.out.println("================== TIME ==========================");
    long startTime = System.nanoTime();
    System.out.println(myClass.largestIntInArrayFaster(b));
    long stopTime = System.nanoTime();
    long elapsedTime = stopTime - startTime;
    System.out.println(elapsedTime);
    System.out.println("==================================================");
  }
{% endhighlight %}

{% include cs_copyright.html %}