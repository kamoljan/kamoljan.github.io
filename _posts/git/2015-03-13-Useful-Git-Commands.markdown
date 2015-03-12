---
layout: post
title:  "Friquently Used Git Commands, Which I use"
date:   2015-03-13 14:35:18
categories: jekyll update
---

###How do you roll back (reset) a Git repository to a particular commit?
{% highlight bash %}
git reset --hard <tag/branch/commit id>
git push <reponame> -f
{% endhighlight %}

###How to cancel a local git commit

{% highlight bash %}
git reset HEAD
{% endhighlight %}