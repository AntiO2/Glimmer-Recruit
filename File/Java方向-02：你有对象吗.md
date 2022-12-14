![](image/Java.png)

# Java方向-02：你有对象吗

> `难度系数`：简单
>  
> Java是一门以面向对象编程为思想设计的语言。相比于提出时间较早、面向过程的C语言等，Java更好的吸收了面向对象的思想，能够优雅、简单地实现面向对象编程。
>  
> 下面两组招新题，将带你学习Java较C语言的最大不同——面向对象思想。


## Part 1. 灵魂拷问

> 题目灵感 ICPC Nanjing 2021: Cloud Retainer's Game


又到过年时节了，Lumine去庆云顶看望孤独的老人Cloud Retainer。没想到刚进洞府，老人就向她抛出了一个灵魂拷问：

> 你有对象吗？


众所周知，你电的学生是找不到对象的。Lumine向你求助，请你帮她找到对象！

### Task 1

Java不能帮你找到对象，但是Java可以帮你新建对象。没有对象？自己new一个不就好了（笑

> 面向对象是一种模式，它提供一种将具体事物抽象为类的思想模式，从事物的特征（属性）和行为（方法）两个方面对事物进行描述和操作。


现在让我们考虑现实中的女朋友。对于一个女朋友，她有她的名字，年龄，身高，颜值等基本的属性，同时她也有约会、吃饭、卷、摆烂等基本行为。

为了骗过Cloud Retainer，我们需要用程序模拟Lumine与对象交互的过程。如果我们使用传统的面向过程方式编程，也就是程序=数据结构+算法的模式下，是不存在“女朋友”这个实体的计算机表示的。这样就导致我们对“女朋友”的信息的储存、行为的管理显得混乱。这时就轮到我们的面向对象编程登场辣。

下面，请学习Java的类（Class）、类的属性和类的方法的基本概念，为Lumine定义一个`Girlfriend`类（`Boyfriend`也行，xp测试题（bushi））。其中应包含上述提到的基本信息（属性），和基本的行为（方法）。

例子：

```java
class Girlfriend{
    String name;
    void bailan(){
        System.out.println(name+"摆烂中！");
    }
} //（仅供参考，请自行完善你喜欢的属性和方法）
```

> 回答要求：
>  
> 按要求定义一个Girlfriend或Boyfriend类，完善这个类的属性和方法。在方法中尝试与属性或其他方法交互。
>  
> 什么是类？什么是类的属性、类的方法？


### Task 2

定义好Girlfriend类了，是否就万事大吉了？当然不是。`女朋友类`仅仅是女朋友的模板罢了。想要真正获得女朋友，你还需要女朋友类的`实例`！

> 类就是对象的**模板**，而**对象**就是类的一个**实例** 。


获得对象的两个步骤：

1. 声明一个该类型的变量。
2. 创建它，为它分配储存空间，然后将该对象的引用赋值给这个变量。一般我们使用new关键字。

所以说获得对象是如此简单（

请你在`主类`的main方法中创建一个你定义的`Girlfriend`类的实例，并给她赋予基本属性，调用她的方法。

例子：

```java
public static void main(String[] args){
        Girlfriend girlfriend1 = new Girlfriend();
        girlfriend1.name = "Klee";
        girlfriend1.bailan();
    } //仅供参考，请自行完善调用其他属性和方法
```

> 回答要求：
>  
> 将要求的代码附在题解中。
>  
> 什么是对象/实例？和类有什么区别？
>  
> 学习instanceof关键字，它有什么作用？
>  
> 了解什么是类的构造方法，给你的类写一个构造方法并使用它。
>  
> 讲讲构造方法是干什么用的？
>  
> 了解this关键字，讲讲它是干什么用的。


## Part 2. Don't touch my Waifu
> Waifu:  指漫画、动画、游戏等中的一些女性角色。有些玩家/观众很喜欢这类角色，并把她们看作像自己的妻子一样的人，故用此名稱。——维基词典


Cloud Retainer看了Lumine在内存上新建的整整1e9个Waifu（即上面你写的类的实例），非常羡慕，她也想像她一样拥有那么多个Waifu。

Lumine有些担心了。她好不容易获得了这么多个Waifu，当然只能给她访问，怎么能让那老婆子随便调用她们的属性和方法？至少那几个关 键的方法不能给别人调用吧。

### Task 3

学习Java的**访问修饰符**，了解不同的访问修饰符对应的访问权限，然后为你的`Girlfriend`类及其属性和方法添加恰当的访问修饰符，保护她们敏感信息的隐私，同时允许外部调用一些不那么敏感的信息（名字等）。

> 回答要求：
>  
> 将要求的代码附在题解中。
>  
> 分别讲讲不同的访问修饰符对应的访问权限，以及应该在什么时候使用它们。
>  
> 为什么要限制外部访问？结合“封装”的知识，谈谈你的理解。
>  
> 了解什么是Java的包，讲讲包有什么作用。
>  
> 新建一个名为`space.glimmer.lumine`的包，将你的类丢进去，尝试从外部访问它。
>  
> 访问时发生了什么？换其他的访问修饰符呢？


### Task 4

Lumine太不放心她内存里的Waifu们了。她想写一个Waifu管理类 `WaifuController` 来统一管理她们。

她要求这个类应该实现以下功能：

- 用一个列表ArrayList（`java.util.List`）来储存所有的Waifu；
- 提供方法删掉指定名字的Waifu；
- 提供方法添加一个Waifu；
- 提供方法返回现有Waifu的数量；
- 其他你喜欢的功能。

Lumine太懒了，她不想每次管理Waifu都操作一个`WaifuController`的实例。有什么方法让`WaifuController`中的信息和方法只存在一个，不创建实例就可以直接调用呢？

> 回答要求：
>  
> 如果没有使用过Java的ArrayList类，可以自行搜索了解。
>  
> 学习属性和方法的 `static` 关键字，完成上述要求的类并将代码附在题解中。
>  
> 如何理解`static`的“静态”的含义？被`static`修饰的成员和其他成员有什么区别？


---

## 本题题解要求

- 认真完成每个Task下的回答要求，记录你的做题过程，遇到的问题和解决方法等，配以必要的截图和说明；
- 用自己的理解回答问题，可以不完全理解知识点，但一定不要照抄网上资料，不得抄袭代码。

## 需要掌握的知识点

- 面向对象编程思想
- java的类和实例
- 构造方法、访问修饰符
- 成员的static关键字

## Tip

- 善用搜索引擎

## 本题提交方式

> 收件邮箱：glimmer401[@outlook.com ](/outlook.com ) 
>  
> 主题格式： 学号-姓名-考核-Java-02
>  
> 主题示例：2022090901012-张三-考核-Java-02


## 出题者联系方式

> tk_sky
>  
> QQ：2071594767
>  
> 邮箱：linhanyuan_km[@163.com ](/163.com ) 

