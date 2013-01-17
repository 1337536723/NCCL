## Lesson 9 Convert a number to a string 整型转字符串
	#include <stdio.h>

	void itoa(int num, char buf[])
	{
		int i = 0;
		int j = 0;

		do 
		{
			buf[i++] = num % 10 + '0';
			num /= 10;		
		} while (num);
		buf[i] = '\0';

		for (j = 0, i--; j < i; j++, i--)
		{
			char tmp;
			
			tmp = buf[i];
			buf[i] = buf[j];
			buf[j] = tmp;
		}

		return;
	}

	int main(void)
	{	
		int num;
		char buf[100];

		printf("Please input a number: ");
		scanf("%d", &num);

		itoa(num, buf);

		printf("number string = %s\n", buf);

		return 0;	
	}

### 知识点
* 数组 array
* 函数式的宏定义
* 进制表示 oct, dec, hex
* 三元表达式 a > b ? a : b
* 字符串逆序 reverse()
* 字符串库函数 itoa 
	
### 课堂讨论
* do-while 的循环可以用 while 循环替换吗？ 为什么？
* 如果要将输入数字，按照16进制，或者2进制转换成字符串，如何修改？
* 为了交换两个字节的内容，示例中引入了一个 tmp 变量，这个是必须的吗？
* 在 itoa 中用到了字符串的逆序操作，请实现一个函数来完成这个操作。

### 课后练习
* 用户任意输入一个字符串，判断这个字符串是否为“回文”(回文即按正反顺序读都一样)。例如 “abcba” 就是回文。
* 使用字符数组实现基于数字字符串的加减法。例如"123" + "45" = "168" , "456"-"13"="443"。
* 编写一个去字符串多余空格的的程序，将连续的多个空格用一个空格代替。例如输入"abc___ab_a__c"，输出"abc ab a c"。

