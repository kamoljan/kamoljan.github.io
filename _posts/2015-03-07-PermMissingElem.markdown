---
layout: post
title:  "PermMissingElem"
date:   2015-03-07 16:56:18
categories: jekyll update
---

###Task description

{% highlight text %}

Task description
A zero-indexed array A consisting of N different integers is given. The array contains integers in the range [1..(N + 1)], which means that exactly one element is missing.
Your goal is to find that missing element.
Write a function:
func Solution(A []int) int
that, given a zero-indexed array A, returns the value of the missing element.
For example, given array A such that:
  A[0] = 2
  A[1] = 3
  A[2] = 1
  A[3] = 5
the function should return 4, as it is the missing element.
Assume that:
N is an integer within the range [0..100,000];
the elements of A are all distinct;
each element of array A is an integer within the range [1..(N + 1)].
Complexity:
expected worst-case time complexity is O(N);
expected worst-case space complexity is O(1), beyond input storage (not counting the storage required for input arguments).
Elements of input arrays can be modified.
{% endhighlight %}

###Solution

{% highlight go %}
package main

import (
    "fmt"
    "sort"
)

func main() {
    fmt.Println("If array is empty.\n Should be 2")
    fmt.Println(Solution([]int{1}))

    fmt.Println("If array is single item.\n Should be 1")
    fmt.Println(Solution([]int{2}))

    fmt.Println("If array is missing last element.\n Should be 4")
    fmt.Println(Solution([]int{2, 3, 1}))

    fmt.Println("If array is missing first element.\n Should be 1")
    fmt.Println(Solution([]int{2, 3, 4}))

    fmt.Println("Normal case.\n Should be 4")
    fmt.Println(Solution([]int{3, 2, 5, 1}))
}

func Solution(A []int) int {
    sort.Sort(sort.IntSlice(A))
    var l = len(A)
    /* If array is empty */
    if l == 0 {
        return 1
    }
    /* If array is single item */
    if l == 1 {
        if A[0] == 1 {
            return 2
        }
    }
    /* If array is missing first element */
    if A[0] != 1 {
        return 1
    }

    var a int = 0
    var cnt int = 0
    for _, v := range A {
        cnt = cnt + 1
        if cnt == 1 {
            a = v
        } else {
            a = a + 1
            if a != v {
                return a
            }
            if cnt == l {
                return v + 1
            }
        }
    }
    return 0
}
{% endhighlight %}