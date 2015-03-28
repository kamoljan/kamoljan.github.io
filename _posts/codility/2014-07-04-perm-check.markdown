---
layout: post
title:  "Codility: PermCheck"
date:   2014-07-04 14:35:18
categories: codility
---

###Task description

{% highlight text %}
A non-empty zero-indexed array A consisting of N integers is given.
A permutation is a sequence containing each element from 1 to N once, and only once.
For example, array A such that:
    A[0] = 4
    A[1] = 1
    A[2] = 3
    A[3] = 2
is a permutation, but array A such that:
    A[0] = 4
    A[1] = 1
    A[2] = 3
is not a permutation.
The goal is to check whether array A is a permutation.
Write a function:
def solution(A)
that, given a zero-indexed array A, returns 1 if array A is a permutation and 0 if it is not.
For example, given array A such that:
    A[0] = 4
    A[1] = 1
    A[2] = 3
    A[3] = 2
the function should return 1.
Given array A such that:
    A[0] = 4
    A[1] = 1
    A[2] = 3
the function should return 0.
Assume that:
N is an integer within the range [1..100,000];
each element of array A is an integer within the range [1..1,000,000,000].
Complexity:
expected worst-case time complexity is O(N);
expected worst-case space complexity is O(N), beyond input storage (not counting the storage required for input arguments).
Elements of input arrays can be modified.
{% endhighlight %}

###Solution in Python

{% highlight python %}
def solution(A):
    A.sort()
    l = len(A)
    if A[0] != 1:
        return 0
    else:
        for i, e in enumerate(A):
            if l != i + 1 and A[i] != A[i+1] - 1
                return 0
    return 1
{% endhighlight %}

###Solution in Java

{% highlight java %}
import java.util.HashMap;
import java.util.Map;

public class MyClass {
  private static final int MAX_LENGTH = 100000;

  public int solution(int[] A) {
    Map<Integer, Boolean> hashMap = new HashMap<Integer, Boolean>();
    long len = A.length;
    if (len > MAX_LENGTH) {
      return -1;
    }
    long actSum = 0;
    long expSum = len * (len + 1) / 2; // sum(1, 2, .. n) => n(n+1)/2
    for (int a : A) {
      actSum = actSum + a;
      Boolean isThere = hashMap.get(a);
      if (isThere == null) {
        hashMap.put(a, true);
      } else {
        return 0;
      }
    }
    return actSum == expSum ? 1 : 0;
  }
}
{% endhighlight %}

Another solution by [Codesays.com](http://codesays.com/2014/solution-to-perm-check-by-codility/)
{% highlight java %}
public static int solution(int[] A) {
        int[] counter = new int [A.length];
 
        for(int i= 0; i< A.length; i++){
            if (A[i] < 1 || A[i] > A.length) {
                // Out of range
                return 0;
            }
            else if(counter[A[i]-1] == 1) {
                // met before
                return 0;
            }
            else {
                // first time meet
                counter[A[i]-1] = 1;
            }
        }
        return 1;
    }
}
{% endhighlight %}

{% include codility_copyright.html %}