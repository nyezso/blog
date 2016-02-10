---
layout: post
title: ! 'Java Puzzle #11: Change argument of foreach'
author: Martin Thoma
date: 2012-10-14 21:15:43.000000000 +02:00
categories:
- Code
tags:
- Programming
- Java
- puzzle
featured_image: 2012/07/java-thumb.png
---
What is the output of the following HelloWorld.java?

{% highlight java %}import java.util.LinkedList;

public class HelloWorld {
    public static void main(String[] args) {
        LinkedList<Integer> list = new LinkedList<Integer>();
        list.add(1);
        list.add(2);
        list.add(3);
        int i = 0;
        for (Integer el : list) {
            System.out.println(el);
            list.add(el);
            i++;
            if (i > 20) {
                break;
            }
        }
    }
}{% endhighlight %}


.
.
.
.
.
.
.
.
.
.
.
.
.
.
.
.
.
.
.
.
.
.
.
.

<h2>Answer</h2>
{% highlight java %}1
Exception in thread "main" java.util.ConcurrentModificationException
	at java.util.LinkedList$ListItr.checkForComodification(LinkedList.java:761)
	at java.util.LinkedList$ListItr.next(LinkedList.java:696)
	at HelloWorld.main(HelloWorld.java:10){% endhighlight %}