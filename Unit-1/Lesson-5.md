## Lesson 5 Summarize all numbers from 1 to 100 ��1�ӵ�100���
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

* �﷨֪ʶ��
	- ѭ����� for
	- �Զ����� i
	- ��ֵ����� +=