## Lesson 23 Five-Chess game 五子棋
	棋子分为黑白两色，棋盘为15×15，棋子放置于棋盘线交叉点上。
	两人对局，各执一色，轮流下一子，先将横、竖或斜线的5个或5个以上同色棋子连成不间断的一排者为胜。

### 语法知识点
* 宏定义 #define
* 二维数组 int chessboard[][]
* 二重循环 for-for
* printf 和 scanf 输入输出
* 运算符 %, ++, 
* 方向表示 (dx, dy) 
* 函数设计 
	
### 参考思路

	#step 1: 画棋盘 10 * 10,  =0
		复习 for 循环 (二重 for 循环)
		复习 printf 打印 %d 的用法
	
	#step 2: 落子 =1, =2
		复习 数组变量，复习 scanf 获取用户输入，&x &y 取地址符	
	
	#step 3: 判断选手 who, step % 2 + 1
		复习 ++ 自增运算符，复习 % 取余(模)运算符
	
	#step 4: 判断落子位置是否合理 is_valid && is_empty
		复习 逻辑与，逻辑或，逻辑取反
	
	#step 5: 如何自动输入？ 
		编辑一个 step.txt 文件，记录两个人的落子位置
		运行时，使用重定向符 <  
	
		举例： ./fivechess < step.txt
	
	#step 6: 判断输赢 is_win
		从 第 0 行开始，第 0 列 到 第 4 列 一共是 5 个位置 a, b, c, d, e
		如果 a 位置的值 == who , 则 计数器加 1 : counter++
		对这 5 个位置 来一个 for 循环，依次判断，
		
			for (j = 0; j < 5; j++)
				chessboard[0][j] == who ?
		
	
		如果for循环结束的时候，counter == 5 ，则说明 win 赢了，否则 则 return 0	;
	
		把上述功能实现为一个函数 check_right(int x, int y, int who);
		完成判别向右方向是否有 5 子连珠的功能，从 x, y 这个位置向右看5个子，是否都是 who 这个人
	
		然后对棋盘二维数组里面的每一个 x, y 位置，进行循环判断，如果其中有一个位置成功，则返回成功1
		如果所有位置都判别完了，但没有返回1，则最后就返回失败 0
	
		根据上面的办法，类似实现其他3个方向的操作： 向下，向右下，向左下 斜线方向 的判别
		check_down(int x, int y, int who);
		check_down_right(int x, int y, int who);
		check_down_left(int x, int y, int who);
	
		如果对于二维棋盘的每一个点，按照 4 个方向都进行一次判别，其中有一个方向成功，则返回成功1
		如果4个方向都没有成功，则取下一个点，再按照这4个方向进行判别，直到所有的点的所有的方向都判别完毕。

### 函数参考设计
	/* display chessboard using printf */
	void print(int board[ROW][COL])
	
	/* get user input */
	int get(int *x, int *y)

	/* put chess in chessboard(x, y) with who 's chess*/
	int put(int x, int y, int who)

	/* test (x, y) is valid before put chess */
	int onboard(int x, int y)

	/* check if (x, y) is empty */
	int empty(int x, int y)

	/* test (x, y) is valid before put chess, call onboard() and empty() */
	int test(int x, int y)	
	
	/* check if (x, y) has 5 chesses */
	int check(int x, int y)
	
	/* check if someone wins */
	int find(void)
	
	/* machine think a good place */
	int think(int *x, int *y)
	
	
### 如何实现机器-机器之间比赛
1. 所有程序必须严格规定输入输出格式，输入是对方落子的位置 x y （用空格间隔），输出是自己计算的下一步位置 x2 y2 
2. 所有打印棋盘的 printf 或者 debug 输出语句，可以采用宏定义方式输出到 stderr，也可以通过 ./log 程序进行过滤
3. 执行之前，必须先用 make p 创建 p1 p2 两个管道文件，然后开2个shell窗口，一个先执行 make t1 ，另一个再执行 make t2，就可以实现机器对战。
4. 执行的结果会保存在 log.txt 文件中，通过 ./replay 就可以实现回放复盘。
	
