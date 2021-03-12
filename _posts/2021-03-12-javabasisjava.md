# java基础学习回顾

学习路径：

-  javase----->mysql数据库----->前端（html,css,js,json,jquery,ajax）----->javaee----->jsp----->代理----->maven----->SSM框架----->linux操作----->radis



# 1、makedown语法

- 推荐编辑器：typora

- 文件后缀：xxx.md

## 二级标题

### 三级标题

#### 四级标题





## 字体

**加粗字体**

*倾斜字体*

***加粗倾斜字体***

~~删除字体~~



## 分割线

***

------

## 图片

![]()





## 超链接



## 表格



## 代码

```java
public void study(){}
```



# 2  java基础



- 下载j安装jdk ,查看安装情况:cmd输入 --->java -version
- 下载安装idea



## 2.1 java的两种核心机制

- JVM:java虚拟机
- GC:垃圾回收机制



## 2.2 标识符和关键字

### 标识符

由字母,数字,下划线,美元符号$组成;

不能以数字开头;

java区分大小写.

- 包名: 字母小写  xxxyyyzzz
- 类名,接口名: 单词首字母大写  XxxYyyZzz
- 变量名,方法名:首字母小写,驼峰命名规范  xxxYyyZzz
- 常量名:全部大写下划线连接  XXX_YYY_ZZZ

### 关键字

| abstract   | assert       | boolean   | break      | byte   |
| ---------- | ------------ | --------- | ---------- | ------ |
| case       | catch        | char      | class      | const  |
| continue   | default      | do        | double     | else   |
| enum       | extends      | final     | finally    | float  |
| for        | goto         | if        | implements | import |
| instanceof | int          | interface | long       | native |
| new        | package      | private   | protected  | public |
| return     | strictfp     | short     | static     | super  |
| switch     | synchronized | this      | throw      | throws |
| transient  | try          | void      | volatile   | while  |

## 2.3 变量

局部变量:必须赋值

成员变量:不赋值,系统会赋默认值



## 2.4 数据类型

八种基本数据类型:

| 整数型                             | 浮点型              | 布尔型     | 字符型  |
| ---------------------------------- | ------------------- | ---------- | ------- |
| byte(1), short(2), int(4), long(8) | float(4), double(8) | boolean(1) | char(2) |

数据类型转换:

byte<short(char)<int<long<float<double

- 自动类型转换:小转大
- 强制类型转换:大转小(可能会损失精度)



引用数据类型





## 2.5 控制语句

接收键盘输入

```java
java.util.Scanner s = new java.util.Scanner(System.in);
int age = s.nextInt();
```

### 选择语句

#### if

```java
if(true|false){
    
}else{}
```

#### switch

```java
switch(字面值或变量){
        case 值:
        	java语句;
        	break;
        case 值:
        	java语句;
        	break;
    	default:
        	java语句;
}
```

### 循环语句

#### for

```java
for(;;){
   循环体; 
}
```

#### while

```java
while(布尔表达式){
    循环体;
}
```

#### do...while

```java
do{
    循环体;
}while(布尔表达式);
```

### 控制循环语句

#### break

​	终止switch语句

​	终止循环

#### continue[下一个]

​	跳过本次循环,直接进入下次循环,不会终止全部循环



## 2.6 类和对象

类是对象抽象的集合

```java
[修饰符列表] class 类名{
    属性;
    方法;
}
```

## 2.7 方法

### 普通方法[实例方法]

```java
[修饰符列表] 返回值类型 方法名(形参){
    方法体;
}
```

### 构造方法

- 当一个类中没有写任何构造方法,则系统默认提供无参构造方法[缺省构造器]

- 如果写了构造方法,则系统不提供无参构造方法

```java
[修饰符列表] 方法名(){
    
}
```

### 静态方法static

带有static修饰的方法,采用:  "类名."的方式访问,不需要new对象,可直接访问

### 方法重载和方法覆盖

**重载(overload)**:在同一个类中,方法名相同

- 数量不同
- 顺序不同
- 类型不同

重载和什么有关,和什么无关?

- 和方法名,参数列表有关

- 和返回值类型无关
- 和修饰符列表无关

**覆盖**:子类调用父类方法,重写父类方法

### 方法递归

方法调用自身

```java
public void doSome(){
    doSome();
}
```



## 2.8 封装private

类的属性私有化,对外提供set和get方法, 重写toString,使数据安全

```java
public class A{
    
    private int age;
        //get方法
    public int getAge(){
        return age;
    }
    	//set方法
    public void setAge(int age){
        this.age = age;
    }
}
```



## 2.9 static和this

### static

- static修饰的是类级别的,

- static修饰的变量是静态变量,

- static修饰的方法是静态方法



### 静态代码块,实例语句块

```java
//静态代码块,类加载时执行,只执行一次,可以写多个
static{
    java语句;
}
//实例语句块,只要执行构造方法,就会在构造方法执行之前执行
{
    java语句;
}
```

### this

- 是一个引用,保存的是当前对象的内存地址,指向对象自身,使用在实例方法中,**不能使用在静态方法中**

- 也可以使用在构造方法中:无参调有参来初始化: this(参数列表);
- 只能使用在构造方法的第一行



## 2.10 继承extends

子类继承父类,只能单继承;如果没有继承,默认继承object类



## 2.11 方法覆盖和多态

### 方法覆盖:

- 有继承关系
- 具有相同的方法名,返回值类型,形式参数列表
- 访问权限不能更低
- 抛出异常不能更多

**静态方法不存在覆盖,私有方法不能覆盖**

### 多态

向上转型

```java
//通过父类型引用指向子类型对象
Animal a = new Cat();
```

向下转型(调用子类型特有的方法,就需要强制类型转换)

```java
Cat c = (Cat) new Animal();
```

向下转型有风险,使用instanceof运算符在运行阶段动态判断引用1指向的类型

```java
(c instanceof Cat)//结果为true或者false
```



## 2.12 super

- 是一个引用,保存的是父类对象的内存地址,指向父类对象,使用在实例方法中,**不能使用在静态方法中**

- 也可以使用在构造方法中:创建子类前,先初始化父类特征: super();
- **子类构造方法执行前,会先执行父类构造方法**
- 只能使用在构造方法的第一行
- **一个类如果既没有super()也没有this()则默认提供super()**
- this()和super()不能共存

- 父中有,子中也有,如果想在子类中访问父类特征,使用super. 不能省略.











