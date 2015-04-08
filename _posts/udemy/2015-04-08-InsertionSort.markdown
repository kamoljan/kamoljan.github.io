---
layout: post
title:  "Introduction To Data Structures Algorithms In Java"
date:   2015-04-08 21:35:18
categories: udemy
---

#### Sorting Algorithm

##### Lecture 27 Assignment 1
Write a class Employee, which represents an employee in a company. 
The employee has a employeeNumber (9 digit number), firstName, lastName and emailId as member variables. 
Create a few employee objects and store them in an array. 
Write the insertion sort algorithm, which takes an array of employee and sorts them in order of their employee number.


#### Java solution

{% highlight java %}
public class Employee {
  int employeeNumber;
  String firstName;
  String lastName;
  String emailId;
  public Employee(int employeeNumber, String firstName, String lastName, String emailId) {
    this.employeeNumber = employeeNumber;
    this.firstName = firstName;
    this.lastName = lastName;
    this.emailId = emailId;
  }
}

public Employee[] hireEmployees(int size) {
  Employee[] employees = new Employee[size];
  Random random = new Random();
  for (int i = 0; i < size; i++) {
    int empNum = random.nextInt(1000000000);
    Employee emp = new Employee(empNum, "FirstName" + empNum, "LastName" + empNum, empNum + "@facebook.com");
    employees[i] = emp;
    System.out.println(emp.employeeNumber);
  }
  return employees;
}

public Employee[] sortEmployeesByInsertionSort(Employee[] employees) {
  System.out.println("Sorted by Insertion Sort Algorithm");
  Employee empTmp;
  for (int i = 0; i < employees.length; i++) {
    int j = i;
    while (j >= 1 && employees[j - 1].employeeNumber > employees[j].employeeNumber) {
      empTmp = employees[j - 1];
      employees[j - 1] = employees[j];
      employees[j] = empTmp;
      j = j - 1;
    }
  }
  return employees;
}

@Test public void main() {
  Employee[] employees = myClass.sortEmployeesByInsertionSort(myClass.hireEmployees(5));
  for (Employee employee: employees) {
    System.out.println(employee.employeeNumber);
  }
}
{% endhighlight %}

#### Result

{% highlight text %}
333564519
204035050
647316866
790917868
106793086
Sorted by Insertion Sort Algorithm
106793086
204035050
333564519
647316866
790917868
{% endhighlight %}

##### Lecture 27 Assignment 2
Write an algorithm which checks if there are duplicate characters in a string. The method signature would look something like public boolean hasDuplicateChars(String s) . If we pass "anaconda" the method should return true (repeated char 'a'). If we pass 'great', the method should return false, because there are no duplicate characters in the string. What is the time complexity of this algorithm? If we know that the string contains ONLY ASCII characters, can we improve the algorithm?

#### Java solution

{% highlight java %}
public boolean hasDuplicateChars(String s) {
  int[] chars = new int[128];
  char c;
  for (int i = 0; i < s.length(); i++) {
    c = s.charAt(i);
    chars[c] = chars[c] + 1;
    if (chars[c] > 1) {
      return true;
    }
  }
  return false;
}
{% endhighlight %}

##### Lecture 27 Assignment 3
Write an algorithm that takes two strings and returns a boolean value indicating if the strings are anagrams. If you don't know what an anagram is, search for the word (not the algorithm) online. What is the time complexity of this algorithm?

#### Java solution

{% highlight java %}
public boolean isAnagram(String a, String b) {
  if (a.length() != b.length()) {
    return false;
  }
  if (a.length() == 0 || b.length() == 0) {
    return false;
  }
  if (a.equals(b)) {
    return false;
  }
  if (a.length() != 0)
    for (int i = 0; i < a.length(); i++) {
      if (b.indexOf(a.charAt(i)) == -1) {
        return false;
      }
    }
  return true;
}
{% endhighlight %}

The example is taken from [Udemy: Introduction To Data Structures Algorithms In Java](https://www.udemy.com/introduction-to-data-structures-algorithms-in-java/)