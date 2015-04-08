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

The example is taken from [Udemy: Introduction To Data Structures Algorithms In Java](https://www.udemy.com/introduction-to-data-structures-algorithms-in-java/)