![](image/c.png)

# C - 01 A + B by C

> 难度系数：入门-简单 保证题目难度与task标号成正比。
>
> C语言作为高级语言中的低级语言（因为更接近底层），C语言程序运行速度明显优于其他语言。从现在开始，你将步入C语言大门，享受C语言的快乐。


## Part 0 Hello, glimmer! 
第一次写某个语言的程序，大家都爱写 `Hello, world!`，那么我们就遵循传统，写 `Hello, glimmer!` 吧（？）。

#### 程序
```c
#include <stdio.h>

int main() {
    printf("Hello, glimmer!");
    return 0;
}
```

### Task 1

尝试自己打码，并编译运行此程序。回答一下问题：

1. 为什么该程序可以打印`Hello, glimmer!`？ 	请尝试解释代码第一行 `#include <stdio.h>`来回答此问题。

2. `int main()` 在代码中起到什么样的作用？


#### Tips

- 善于使用搜索引擎
- C语言的头文件（标准库）
- 编译的预处理阶段
- 程序的主函数

## Part 1 C == C++
写程序有什么用呢？当然是用程序完成复杂的运算。~~（简单的运算手算不比打码快？）~~

### Task 2 A + B problem (easy version)
编写一个程序，完成 a + b 计算。

#### tips

- C语言支持的数据类型。
	>参考[C语言数据类型](https://www.runoob.com/cprogramming/c-data-types.html)

- C语言提供的运算符
	>参考[C语言运算符](https://www.runoob.com/cprogramming/c-operators.html)

- C语言提供的数据结构
	>了解一下`数组`，`struct`，`union`，`enum`。

### Task 3

1. 描述一下 `=` 和 `==` 两个运算符的区别。
2. 描述一下`struct` 和 `union` 的区别。
3. 二进制如何表示一个实数呢？**（选做）**
4. 试解释，为什么`float`数据类型不能准确的表示所有实数？**（选做）**

## Part 2 C~~ode~~For~~ces~~
我们调试上述程序发现程序是一条一条语句执行~~（这不废话吗）~~。这就是最基础的顺序结构。
然而顺序结构并不能解决所有问题。举个例子，如何向管理员和普通用户提供不同的程序服务？我们的选择结构就派上用场了。
假设我们要求1到10000之间所有数的和（不用公式），你不会真要写10000行代码吧？这个时候我们的循环结构就派上用场了。
为了使程序更便于我们阅读，我们并不会将全部代码都放置在`main`函数中，我们可以自己手写功能函数，使整个代码看起来简单明了。[什么是函数](https://www.runoob.com/cprogramming/c-functions.html)

### Task 4

阅读下列程序，完成以下任务：
```c
#include <stdio.h>

int func(int);

int main() {
    int n;
    scanf("%d", &n);
    printf("%d", func(n));
    return 0;
}

int func(int n) {
    return n <= 2 ? 1 : func(n - 1) + func(n - 2);
}
```

1. `func`函数的作用是什么？
2. 描述`int func(int);`各个部分的含义。
3. 试描述`main`函数中n，与`func`函数中n的区别。
4. 如果输入`1000000`，输出的是什么。
5. 尝试修改代码，使该程序有输出，此时，你的输出结果正确吗？如不正确，请修改程序。


#### tips

-  函数递归。 
-  考虑一下int可以表示的数据范围。 

## Part 3 Test（选做）
至此，小伙伴们应该能流畅的写程序辣。（~~好像每个程序都是由三大程序结构组成的。~~）
为了结束枯燥的入门知识学习，让我们秒个题放松放松，顺便检测一下大家前述知识的掌握情况。

### Task 5 A + B problem (hard version)

#### Description
> **血的教训：大一要学好微积分和线代，学好微积分和线代，学好微积分和线代。**（出题人感慨，与此题无关）

下列有1个n元一次方程组：
![](image/e720812b88ef705ccb6e8f9a52f2d9bb.svg)
**保证**$$b_1$$**到**$$b_n$$**严格单调递增**。_MOD 表示取余_，对应的运算符为`%`。$b_i$保证在int整型数据范围内。
求$$a_{1}$$到$$a_n$$的一组可行解。

#### input

第一行一个整数n。
第二行n个整数，表示$$b_1$$到$$b_n$$。

#### output
一行n个整数，表示$$a_{1}$$到$$a_n$$。

#### sample input
```
3
1 3 4
```

#### sample output
```
12 11 4（答案不唯一）
```

#### tips

-  Just an A + B problem.
-  递推。 

## 题目要求

- 正确的可执行的代码
- 回答题目中的问题时，表达自己的想法
- 良好的代码习惯（加分项）
- 代码运行的截图
- 请提交PDF文档


## 本题提交方式
> 收件邮箱：glimmer401@outlook.com 
>
> 主题格式： 学号-姓名-考核-C-01
>
> 主题示例：2022090101012-张三-考核-C-01

## 出题人联系方式
> QQ：2398696309
>
> 邮箱：2398696309@qq.com  
