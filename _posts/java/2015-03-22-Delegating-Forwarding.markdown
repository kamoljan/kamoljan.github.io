---
layout: post
title:  "OOP: Delegation & Forwarding"
date:   2015-03-22 21:35:18
categories: OOP
---

#### Delegation

{% highlight java %}
interface I {
	void f();
	void g();
}
 
class A implements I {
	public void f() { System.out.println("A: doing f()"); }
	public void g() { System.out.println("A: doing g()"); }
}
 
class B implements I {
	public void f() { System.out.println("B: doing f()"); }
	public void g() { System.out.println("B: doing g()"); }
}
 
class C implements I {
	I i = null;
	// delegation
	public C(I i){ setI(i); }
	public void f() { i.f(); }
	public void g() { i.g(); }
 
	// normal attributes
	public void setI(I i) { this.i = i; }
}
 
public class Main {
	public static void main(String[] arguments) {
		C c = new C(new A());
		c.f();	// output: A: doing f()
		c.g();	// output: A: doing g()
		c.setI(new B());
		c.f();	// output: B: doing f()
		c.g();	// output: B: doing g()
	}
}
{% endhighlight %}

The example is taken from [Wikipedia](http://en.wikipedia.org/wiki/Delegation_pattern#Complex_Java_example)

#### Forwarding

{% highlight java %}
public class Stack {
    private java.util.ArrayList list;
    
    public Stack() {
        list = new java.util.ArrayList();
    }
    
    public boolean empty() {
        return list.isEmpty();
    }
    
    public Object peek() {
        if( !empty() ) {
            return list.get( 0 );
        }
        return null;
    }
    
    public Object pop() {
        if( !empty() ) { 
            return list.remove( 0 );
        }
        return null;
    }
    
    public Object push( Object item ) {
        list.add( 0, item );
        return item;
    }   
}
{% endhighlight %}

The example is taken from [JavaWorld](http://www.javaworld.com/article/2077357/learn-java/delegates.html)