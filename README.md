NCCL - New Concept C Language
=============================

please use <http://codepad.org/> to run/test these C programs!

# Unit One
## Lesson 1 What is a simplest C program? (最简单的C程序)
	int main(void)
	{
		return 0;
	}

* 语法知识点
	- 数据类型 int 
	- 函数 main 
	- 函数参数 void 
	- 函数返回值 return 


## Lesson 2 Let's say hello to world (打印输出)
	#include <stdio.h>

	int main(void)
	{
		printf("hello, world!\n");
		return 0;
	}

* 语法知识点
	- 预处理 include
	- 头文件 stdio.h
	- 标准库函数 printf
	- 字符串
	- 转义字符 \n


## Lesson 3 Count how many fingers do you have? (循环打印)
	#include <stdio.h>

	int main(void)
	{
		int counter;

		printf("hello, NCCL!\n");
		
		counter =  0;
		while (counter <= 10)
		{
			printf("counter = %d\n", counter);
			counter++;
		}

		return 0;
	}

* 语法知识点
	- 局部变量
	- 定义和声明
	- 循环语句 while
	- 比较表达式 <=
	- 自增运算符 ++
	- 格式化输出 %d

## Lesson 4 Judge a number odd or even (判断奇偶)
	#include <stdio.h>

	int main(void)
	{
		int num;

		printf("please input a number: ");
		scanf("%d", &num);

		if (num % 2 == 0)
			printf("number %d is even\n", num);
		else	
			printf("number %d is odd\n", num);

		return 0;
	}

* 语法知识点
	- 标准输入函数 scanf
	- 取地址符 &
	- 取模运算符 %
	- 条件语句 if/else
	- 关系运算符 ==

## Lesson 5 Summarize all numbers from 1 to 100 (从1加到100求和)
	#include <stdio.h>

	int main(void)
	{
		int sum = 0;

		for (int i = 0; i <= 100; i++)
		{
			sum += i;
		}

		printf("sum = %d\n", sum);

		return 0;
	}

* 语法知识点
	- 循环语句 for
	- 自动变量 i
	- 赋值运算符 +=

## Lesson 6 Print 9*9 multiplication table (乘法表)
	#include <stdio.h>

	int main(void)
	{
		int sum;
		int i, j;

		for (i = 1; i < 10; i++)
		{	
			for (j = 1; j <= i; j++)
			{
				printf("%d*%d=%d\t", j, i, i * j);
			}
			printf("\n");
		}

		return 0;
	}

* 语法知识点
	- 嵌套循环语句 for-for
	- 二层逻辑嵌套  

Output:

	1*1=1	
	1*2=2	2*2=4	
	1*3=3	2*3=6	3*3=9	
	1*4=4	2*4=8	3*4=12	4*4=16	
	1*5=5	2*5=10	3*5=15	4*5=20	5*5=25	
	1*6=6	2*6=12	3*6=18	4*6=24	5*6=30	6*6=36	
	1*7=7	2*7=14	3*7=21	4*7=28	5*7=35	6*7=42	7*7=49	
	1*8=8	2*8=16	3*8=24	4*8=32	5*8=40	6*8=48	7*8=56	8*8=64	
	1*9=9	2*9=18	3*9=27	4*9=36	5*9=45	6*9=54	7*9=63	8*9=72	9*9=81	

## Lesson 7 Find a max prime number within 100 (求100以内的最大素数)
	#include <stdio.h>
	#include <math.h>

	int main(void)
	{
		int sum;
		int i, j;
		int max = 0;
		int tmp;

		for (i = 1; i <= 100; i++)
		{
			tmp = (int)sqrt(i);

			for (j = 2; j <= tmp; j++)
			{
				if (i % j == 0)
					break;
			}

			if (j == tmp + 1)
				max = i;
		}

		printf("max = %d\n", max);

		return 0;
	}

* 语法知识点
	- 数学头文件 math.h
	- 数学库函数 sqrt
	- 强制类型转换 (int)
	- 三层逻辑嵌套

## Let's have a break here!

## Lesson 8 Josephus ring (约瑟夫环)
* 语法知识点
	- 数组 array
	- 数据驱动编程
	- 复杂逻辑训练

## Lesson 9 Find how many 9 in number 1 to 100 (1到100有多少个9)
* 语法知识点
	- 函数设计 function
	- 逻辑分解

## Lesson 10 Calculate the distance between 2 point (求两个坐标点之间的距离)
* 语法知识点
	- 结构体 struct
	- 结构体传参数

## Lesson 11 Does your machine use little-endian? (判断机器存储是否小尾端)
* 语法知识点
	- 联合 union
	- 字符数组类型 char buf[4]
	- 存储格式 big/little endian	

## Lesson 12 Sorry, your car is restricted today (对不起，你的车今天限行)
* 语法知识点
	- 枚举 enum
	- 分支语句 switch-case

## Lesson 13 Is there a way out? (判断地图上某点是否有出路)
* 语法知识点
	- 二维数组 a[][]
	- 随机函数 rand()
	
## Lesson 14 Convert a number to a string (整型转字符串)
* 语法知识点
	- 进制表示 oct, dec, hex
	- 三元表达式 a > b ? a : b
	- 字符串逆序 reverse()
	- 字符串库函数 itoa 
	
## Let's have a break here!

## Lesson 15 Count how many bit 1 in a number (统计一个数二进制表示中1的个数)
* 语法知识点
	- 位操作 &, |, ~, ^
	- 优化算法效率 <http://hi.baidu.com/bobchennan/item/169952dc515045e4795daa10>
	
## Lesson 16 
* 语法知识点
	- 位域	
	
## Lesson 17 
* 语法知识点
	- 指针

## Lesson 18 
* 语法知识点
	- 函数指针

## Lesson 19 
* 语法知识点
	- 指针数组

## Lesson 20 

## Lesson 21 

## Lesson 22 Guess what number in my hand (猜数游戏)
	猜数游戏：电脑随机产生4位数，然后用户输入4位数，电脑告诉你是?A?B
	请你最后猜出电脑的4位数是多少？	
	(A表示位置和数字都对，B表示位置不对，数字对)

* 语法知识点
	- 基本输入输出
	- 字符串转整数
	- 一维数组
	- while/for/if/else/break
	- 函数设计
	- 二层循环
	- 位操作

## Lesson 23 
## Lesson 24 

# Unit Two
## Lesson 25 
## Lesson 26 
## Lesson 27 
## Lesson 28 
## Lesson 29 
## Lesson 30 
## Lesson 31 
## Lesson 32 
## Lesson 33 
## Lesson 34 
## Lesson 35 
## Lesson 36 
## Lesson 37 
## Lesson 38 
## Lesson 39 
## Lesson 40 
## Lesson 41 
## Lesson 42 
## Lesson 43 
## Lesson 44 
## Lesson 45 
## Lesson 46 
## Lesson 47 
## Lesson 48 

# Unit Three
## Lesson 49 
## Lesson 50 
## Lesson 51 
## Lesson 52 
## Lesson 53 
## Lesson 54 
## Lesson 55 
## Lesson 56 
## Lesson 57 
## Lesson 58 
## Lesson 59 
## Lesson 60 
## Lesson 61 
## Lesson 62 
## Lesson 63 
## Lesson 64 
## Lesson 65 
## Lesson 66 
## Lesson 67 
## Lesson 68 
## Lesson 69 
## Lesson 70 
## Lesson 71 
## Lesson 72 

# Unit Four
## Lesson 73 
## Lesson 74 
## Lesson 75 
## Lesson 76 
## Lesson 77 
## Lesson 78 
## Lesson 79 
## Lesson 80 
## Lesson 81 
## Lesson 82 
## Lesson 83 
## Lesson 84 
## Lesson 85 
## Lesson 86 
## Lesson 87 
## Lesson 88 
## Lesson 89 
## Lesson 90 
## Lesson 91 
## Lesson 92 
## Lesson 93 
## Lesson 94 
## Lesson 95 
## Lesson 96 

