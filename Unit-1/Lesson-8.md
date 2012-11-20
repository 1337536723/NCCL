﻿## Lesson 8 Find how many 9 in number 1 to 100 1到100有多少个9
	/*
	 * main.c - find how many DIGIT from A to B
	 *
	 * Copyright (C) AKAE - li ming <limingth@sina.com>
	 *
	 * 
	 */
	#include <stdio.h>

	/*
	 * find - calculate how many digit in num
	 * @num:	the number we want to find
	 * @digit:	the digit we search in num
	 *
	 * Return value:  how many digit in this num
	 *
	 */
	int find(int num, int digit)
	{
		int counter = 0;	/* the result of how many digit in num */

		do {
			/* get the last digit of num */
			if (num % 10 == digit)
				counter++;

			/* get rid of the last digit */
			num = num / 10;
		} while (num != 0);

		return counter;
	}

	int main(void)
	{
		int begin = 0;		/* the begin number */
		int end = 100;		/* the end number */
		int i = 0;
		int sum = 0;		/* the result of sumary */

		/* calculate how many 9 in 1 to 100 */
		for (i = begin; i <= end; i++) {
			sum += find(i, 9);
		}

		printf("sum = %d \n", sum);

		return 0;
	}
	
### 知识点
* 函数 Function
* 形参和实参
* 函数返回值
* 逻辑分解
* 注释的写法

### 课堂讨论
* 示例中的 0, 100 为何要用 begin, end 来定义，直接写在 for 循环中可以吗？
* find 中的 do-while 改成 while 可以吗？

### 课后练习
* 

### 名人警句
人类短期记忆能够容纳的不连续信息数就是7,7加2或者减2。
