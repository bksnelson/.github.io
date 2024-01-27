---
layout: project
type: project
image: img/java/java.png
title: "Statistician"
date: 2022
published: true
labels:
  - Class project
  - Java
summary: "Java project that collects and stores sequences."
---
This class project is a bag class that collects and stores double sequences with the ability to rectrieve different types of information from it. The project focuses on the concept of information collection in bags and the creation of classes that use methods and static methods. It also has the ability to combine different sequences of numbers with the combination of two objects. This Statistician class provides a flexible and reusable solution for statistical analysis of double sequences, adhering to best practices in Java programming.

```java
public class Statistician
{   
    //Instance fields
    private int length;
    private double sum;
    private double mean;
    private double min;
    private double max;
    private double lastNum;
    
    //Constructor that sets everything to 0 or NaN for a baseline object
    public Statistician()
    {       
        this.length = 0;
        this.sum = 0;
        this.mean = 0;
        this.lastNum = 0;
        this.min = 0;
        this.max = 0;
    }
```
```java
    public void addAll(Statistician addend)
    {   
        if(addend == null)     
            throw new NullPointerException("Null object used");      
        else if(length == 0){
            this.min = addend.min;
            this.max = addend.max;
            this.lastNum = addend.lastNum;
            this.length = addend.length;
            this.sum = addend.sum;
            this.mean = addend.mean;            
        }    
        else if(addend.length != 0){
            if(min > addend.min)
                this.min = addend.min;
            if(max < addend.max)
                this.max = addend.max;
            this.lastNum = addend.lastNum;
            this.length += addend.length;
            this.sum += addend.sum;
            this.mean = sum/length;   
        }

    }  
```
```java
    public static Statistician add(Statistician s1, Statistician s2)
    {      
        //Null object test
        if(s1 == null || s2 == null)     
            throw new NullPointerException("Null object used");   
        else{
            Statistician s3 = new Statistician();
            s3.addAll(s1);
            s3.addAll(s2);
            
            return s3;
        }
    }
```
