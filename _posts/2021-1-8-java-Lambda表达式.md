---
title: Java8学习—Lambda表达式
date: 2021-1-8 23:29:53
categories:
- Java基础
tags:
- Java基础
---

## 1、什么是Lambda表达式？

​       我们可以把Lambda表达式理解为简洁的表示可传递的匿名函数的一种方式：它没有名称，但它有**参数列表、函数主题、返回类型**，可能还有一个可抛出的异常列表。

   ![]({{ site.url }}/assets/img/java8/1.1.png)


   Lambda表达式包括三部分：

​    （1）参数列表—这里它采用了Comparator中compare方法的参数，两个Apple。

​    （2）箭头—把参数列表和Lambda主体分隔开

​    （3）Lambda主体—比较两个Apple的重量，表达式就是Lambda的返回值。

  为了进一步说明Lambda表达式，下面举了五个例子。

​     ![]({{ site.url }}/assets/img/java8/1.2.png)


​     ![]({{ site.url }}/assets/img/java8/1.3.png)


## 2、如何使用Lambda表达式？

###   2.1、什么是函数式接口？

​         **函数式接口**就是只定义一个抽象方法的接口。如下所示：

​        ![]({{ site.url }}/assets/img/java8/1.4.png)


###   2.2、什么是函数描述符？

​          函数式接口的抽象方法的签名基本上就是Lambda表达式的签名。我们将这种抽象方法叫做**函数描述符**。

​       ![]({{ site.url }}/assets/img/java8/1.5.png)


###  2.3、使用局部变量

​          Lambda可以没有限制地捕获实例变量和静态变量，但**局部变量必须显示的声明为final或事实上是final**。

###  2.4、方法引用

​        方法引用可以被看作是仅仅调用特定方法的Lambda的一种快捷写法。它的基本思想，如果一个Lambda代表的只是“直接调用这个方法”，那最好还是用名称来调用它。而不是去描述如何调用它。

​         ![]({{ site.url }}/assets/img/java8/1.6.png)


​       方法引用主要有三类：

​        （1）指向静态方法的方法引用（例如Integer的的parseInt方法，写作Integer::parseInt）。

​        （2）指向任意类型实例方法的方法引用（例如（String s）—>s.toUpperCase()，写作String::length）。

​        （3）指向现有对象的实例方法的方法引用（假设**局部变量**T有getValue方法，则可以写成T::getValue）。



