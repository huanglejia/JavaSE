# 1、Java基础知识图谱     

![image-20201110150413994](C:\Users\huanglejia\AppData\Roaming\Typora\typora-user-images\image-20201110150413994.png)

# 2、Java技术体系

## Java SE(Java Standard Edition)标准版

支持面向桌面级应用的Java平台，提供了完整的Java核心API。

## Java EE(Java Enterprise Edition)企业版

是为开发企业环境下的应用程序提供的一套解决方案。该技术体系中包含的技术如Servlet、JSP等，主要针对于Web应用的开发。

## Java ME(Java Micro Edition)微机版

支持Java程序运行在移动终端（手机，PDA）上的平台，对Java API有所精简，并加入了针对移动终端的支持。

# 3、Java的主要特性

- **Java语言是易学的**。语法与C语言和C++很接近，容易上手
- **Java语言是面向对象的**。Java语言提供类、接口和继承等原语，为了简单起见，只支持类之间的单继承，接口之间的多继承，并支持类与接口的实现机制（implements）
- **Java语言是分布式的**。Java语言支持Internet应用的开发，并提供了一个网络应用编程接口(java.net)

- **Java语言是健壮的**
- **Java语言是安全的**
- **Java语言是解释型的**
- **Java语言是原生支持多线程的**

# 4、Java语言的三大特性

## 封装

### 什么是封装

封装就是把对象的属性和操作结合为一个独立的整体，并尽可能隐藏对象的内部实现细节

- 将类的某些信息隐藏在类的内部，不允许外部程序进行直接的访问调用
- 通过该类提供的方法来实现对隐藏信息的操作和访问
- 隐藏对象的信息
- 留出访问的对外接口

### 封装的特点

- 对成员变量实行更准确的控制
- 封装可以隐藏内部程序实现的细节
- 良好的封装能够减少代码之间的耦合性
- 外部成员无法修改已封装好的程序代码
- 方便数据检查，有利于保护对象信息的完整性，同时也提高程序的安全性
- ‘便于修改，提高代码的可维护性

### 封装的示例

```java
public class User {
    private String id;
    private String name;
   
    public String getId() {
        return id;
    }

    public void setId(String id) {
        this.id = id;
    }

    public String getName() {
        return name;
    }
    
    public void setName(String name) {
        this.name = name;
    }
}

```

对象中的属性是私有的，外部成员无法直接访问，只能通过公共的get set方法来访问，保证了程序的安全性

## 继承

### 什么是继承

继承就是子类继承父类的特征和行为，使得子类对象具有父类的属性和方法，当然，如果父类中的属性和方式是私有属性（private）修饰的，那么子类是不能被继承的。

子类只支持单继承，即一个子类只允许有一个父类，但是可以实现多级继承。

子类可以拥有父类的属性和方法

子类可以拥有自己的属性和方法

子类可以重写覆盖父类的方法

### 继承的特点

提高代码的复用性

父类的属性方法可以用于子类

可以轻松的定义子类

使程序设计变得简单

### 继承的使用

创建的对象是谁，就优先使用谁，如果没有，则直接向上查找。

无论是成员变量还是成员方法，如果没有都是向上父类中查找的，绝对不会向下查找的。

### 多态

### 什么是多态

多态是同一个行为具有多个不同表现形式或形态的能力

### 多态的特点

1、消除类型之间的耦合关系，实现低耦合

2、灵活性

3、可扩充性

4、可替换性

### 多态的体现形式

- 继承
- 父类引用指向子类
- 重写

### 多态的使用

```
package com.lejia.controller;

public class PolymorphismTest {

    public static void main(String[] args) {
        Animal cat = new Cat();
        Animal rabbit = new Rabbit();
        cat.walk();				//猫能够run
        rabbit.walk();			//小兔子能够Jump
    }
}
class Animal{
    public void walk(){
        System.out.println("动物都能够walk");
    }
}
class Cat extends  Animal{
    public void walk(){
        System.out.println("猫能够run");
    }
}
class Rabbit extends  Animal{
    public void walk(){
        System.out.println("小兔子能够Jump");
    }
}

```

正所谓：多态就是一个事物的多种形态

值得注意的是：在编译时，我们看左边的类，也就是说，声明的子类cat与rabbit必须调用的是父类中共有的方法才能够通过编译

在运行时，我们看右边的类，就是实际执行时，我们实际运行的是子类重写后的方法

# 5、Java的两种核心机制

## Java虚拟机(Java Virtal Machine)

JVM是一个虚拟的计算机，具有指令集并使用不同的存储区域。负责执行指令，管理数据、内存、寄存器  

## 垃圾收集机制(Garbage Collection)

垃圾回收在Java程序运行过程中自动进行，程序员无法精确控制和干预  

# 6、JDK、JRE、JVM的关系

## JDK（Java Development Kit）Java开发工具包

JDK是提供给Java开发人员使用的，其中包含了Java的开发工具，也包含JRE

## JRE（Java Runtime Environment）Java运行环境

包含JVM和Java程序所需的核心类库等，如果想要运行一个开发好的Java程序，计算机中只需安装JRE即可

![image-20201110195856274](C:\Users\huanglejia\AppData\Roaming\Typora\typora-user-images\image-20201110195856274.png)

![image-20201110200247854](C:\Users\huanglejia\AppData\Roaming\Typora\typora-user-images\image-20201110200247854.png)

