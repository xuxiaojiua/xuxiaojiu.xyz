---
layout: post
title: java基础进阶回顾
categories: Java
description: java基础进阶
keywords: Java
---



# java学习进阶回顾





## 1、 final

final修饰的变量通常加上static修饰，称为常量

一般是公开的

常量名建议全部大写，每个单词之间用下划线衔接

```java
public static final int COUNT = 10;
```



【了解】

- final修饰的类无法被继承

- final修饰的方法无法被覆盖

- final修饰的实例变量，必须手动赋值，不会采用系统默认值

- final修饰的局部变量只能赋一次值，不能重新赋值



## 2、 抽象类abstract

不能创建对象，但有构造方法

抽象类中不一定有抽象方法，可以有非抽象方法

抽象方法：没有方法体，只能在抽象类中

**没有方法体，不一定是抽象方法，底层调用的C++动态链接库也可以没有方法体，方法的修饰符是native**



```java
[修饰符列表] abstract class A{
    public abstract void doSome();
}
```

非抽象类继承抽象类，必须将抽象方法实现

## 3、 接口

完全抽象的，特殊的抽象类，一个类可以实现多个接口，一个接口可以继承多个接口

无构造方法

只有常量和抽象方法

方法public abstract可以省略

常量的public static final可以省略

extends和implement可以同时使用，extends在前，implement在后

```java
public interface A{
    int b();
    void c();
}
```







## 4、访问控制权限

范围：public > protected > 默认 >private

在哪可以使用：

- 属性：四个都能用
- 方法：四个都能用
- 类：public和默认能用
- 接口：public和默认能用

```java
//公共的，任何位置都可以访问
public int a;
//私有的，只能在本类访问
private int b;
//受保护的，可以在本类，同包，子类中访问
protected int c;
//默认，只能在本类，同包下访问
int d;

```



## 5、Object类

jdk类库的的根类：object类

String类重写了toSting和equals方法

### 5.1 toString

- 将对象转换称字符串形式，需要重写

### 5.2 equals

- 判断两个对象是否相等，默认比较的是内存地址，需要重写

### 5.3 hashcode

- 获取对象的哈希值

### 5.4 finalize

- 垃圾回收机制负责调用，重写后不需要程序员手动调用，如果希望在对象销毁时机执行一段代码，可以写到finalize()方法中
- System.gc();建议启动垃圾回收器

```java
//重写，不需要调用
protected void finalize() throws throwable{
    System.out.println("即将被销毁");
}
```

### 5.5 clone

- 负责对象克隆



## 6、 内部类

了解

匿名内部类

- 使用idea的快捷键alt + enter可自动实现

```java
//调用st对象的doSome方法
Student st = new Studnet();
//st.doSome(接口实现类对象，其他参数)；

//使用匿名内部类不需要将接口实现，直接new 接口{}

//st.doSome(new 接口(){},其他参数..)
//此接口的实现类没有名字
st.doSome(new 接口(){
    接口方法的实现
},其他参数..);
```



## 7、数组





## 8、 String类的21中常用方法







