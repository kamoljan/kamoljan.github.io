---
layout: post
title:  "OOP: Composition & Aggregation"
date:   2015-03-22 14:35:18
categories: OOP
---

#### Composition - "part-of"

{% highlight java %}
public class Car {

  // final will make sure engine is initialized
  private final Engine engine;

  public Car() {
    engine = new Engine()
  }

}

public class Engine {
  private String type;
}

{% endhighlight %}

#### Aggregation - "has"

{% highlight java %}
public class Student {

  Address studentAddress;

  public Student(Address address) {
    this.studentAddress = address;
  }
}

public class Address {
  String street;

  public Address(String street) {
    this.street = street;
  }
}

{% endhighlight %}