# 第一周  程序设计与C语言

```c
#include <stdio.h>
int main() {
    printf("%d\n",12+34);
    
    return 0;
}

```
%d表示后面有一个整数要输出在这个位置上

# 第二周  计算

## 2.1  变量

```c
scanf("%d,&price");
```
要求scanf()这个函数读入下一个整数，读到的结果赋值给变量price

出现在scanf()格式字符串里面的东西，是它一定要你输入的东西

小心&

```c
scanf("%d %d", &a, &b);
scanf("%d,%d", &a, &b);    //两种写法都是对的
```



**判断题：**
给定以下代码段：
int a,b=0;
则a的初始值是0  (x)

```c
#include <stdio.h>

int main(){
    int price = 0;  //定义了一个变量，名字是price，类型是int，初始值为0
    printf("请输入金额：（元）");
    scanf("%d",&price);
    
    int change = 100 - price;
    printf("找您%d元\n",change);
    
    return 0;
}

```

整数 int 
printf("%d",...)
scanf("%d",...)

带小数点的数 double
printf("%lf",...)
scanf("%lf",...)

计算时间差
```c
#include <stdio.h>
int main() {
    int hour1, minute1;
    int hour2, minute2;

scanf("%d %d", &hour1, &minute1);
scanf("%d %d", &hour2, &minute2);

int t1 = hour1 * 60 + minute1;
int t2 = hour2 * 60 + minute2;

int t = t2 - t1;

printf("时间差是%d小时%d分",t/60,t%60);

return 0;
}

```

**前缀后缀**
a++的值是a+1以前的值，++a的值是加了1以后的值，无论哪个，a自己的值都加了1

# 第三周 循环与判断

条件    = = ：相等

do-while循环和while循环很像，唯一的区别是我们在循环体执行结束的时候才来判断条件。也就是说，无论如何，循环都会执行至少一遍，然后再来判断条件。与while循环相同的是，条件满足时执行循环，条件不满足时结束循环。



**判断位数**

```c
#include <stdio.h>
int main() {
    int x;
    int n = 0;
    
    scanf("%d",&x);
    
    x /= 10;
    n++;
    
    while(x>0){
        x /= 10;
        n++;
    }
    printf("%d",n);
    return 0;
    
}
```



**do-while循环**

在进入循环的时候不做检查，而是在执行完一轮循环体的代码之后，再来检查循环的条件是否满足，如果满足则继续下一轮循环，不满足则结束循环



do-while循环和while循环很像，区别是在循环体执行结束的时候才来判断条件，也就是说无论如何循环都会执行至少一遍，然后再来判断条件。与while循环相同的是，条件满足时执行循环，条件不满足时结束循环



**n的阶乘**

```c
#include <stdio.h>
int main() {
    int x;
    int n = 1;
    scanf("%d",&x);
    while(x>1){
        n= n * x;
        x--;
            }
    printf("n = %d",n);
            
return 0;
    
}
```



**循环次数**

for(i=0;i<n;i++)



**Tips for loops**

- 如果有固定次数，用for
- 如果必须执行一次，用do-while
- 其他情况用while

<img src="/Users/draven/Library/Application Support/typora-user-images/image-20210319215801292.png" alt="image-20210319215801292" style="zoom:33%;" />



**bool**

- #include<stdbool.h>
- 之后就可以使用bool和true、false



**逻辑运算**

&&	逻辑与：   	a&&b

||	  逻辑或： 	  a||b



取值范围	x>4&&x<6

!age<20：先判断!age，age是0的话，则!age=1，age不是0的话，则!age=0

再去和20作比较，即可得出整个式子是0还是1  

! > && > ||



**短路**

逻辑运算是自左向右进行的，如果左边的结果已经能够决定结果了，就不会做右边的计算



不要把复制，包括复合赋值组合进表达式



**条件运算符**

- count = (count > 20) ? count - 10 : count + 10;
- 条件、条件满足时的值和条件不满足时的值
- 条件运算符的优先级高于赋值运算符，但是低于其他运算符



i = (3+4,5+6);		//结果是11

else总是和最近的那个if匹配（有大括号时不一定）



**Tips**

- 在if或else后面总是用{}，即使只有一条语句的时候



**switch-case**

switch（控制表达式）{		//控制表达式只能是整数型的结果

case 常量：					//常量可以是常数，也可以是常数计算的表达式

​	语句								//在执行完分支中的最后一条语句后，如果后面没有break，就会顺序执行到下面的case里去，

​	......									//直到遇到一个break，或者switch结束为止

case 常量：

​	语句

​	......

default：

​	语句

​	......

}



<img src="/Users/draven/Library/Application Support/typora-user-images/image-20210320104639980.png" alt="image-20210320104639980" style="zoom:33%;" />

**算平均数**

```c
#include <stdio.h>
int main() 
{
     int number;
     int sum = 0;
     int count = 0;
     
     scanf("%d",&number);
     while ( number != -1 ) {
         sum += number;
         count ++;
         scanf("%d",&number);
     } 
     
     printf("%f\n", 1.0*sum/count);
     
     return 0;
    
}
```



**猜数游戏**

1.让计算机来想一个数，然后让用户来猜，用户每输入一个数，就告诉它是大了还是小了，直到用户猜中为止，最后还要告诉用户猜了多少次

2.因为需要不断重复让用户猜，所以需要用到循环

3.在实际写出程序之前，我们可以先用文字描述程序的思路

4.核心重点是循环的条件



--思路--

1.计算机随机想一个数，记在变量number里；

2.一个负责计次数的变量count初始化为0；

3.让用户输入一个数字a；

4.count++

5.判断a和number的大小关系，如果a大就输出“大”，如果a小就输出“小”

6.如果a和number是不相等的，程序就转回到第3步

7.否则程序输出“猜中”和次数，然后结束

```c
#include <stdio.h>
#include <time.h>
int main() 
{
    srand(time(0));
    int number = rand()%100+1;
    int count = 0;
    int a = 0;
    printf("我已经想好了一个1到100之间的数。");
    do {
        printf("请猜这个1到100之间的数：");
        scanf("%d",&a);
        count ++;
        if ( a > number ) {
            printf("你猜的数大了。");
        } else if ( a < number ) {
            printf("你猜的数小了。");
        }
    }   while (a != number);
    printf("牛逼啊兄弟，用%d次就猜到了。\n",count);
    
    return 0;
    
}
```

随机数

- 每次召唤rand()就得到一个随机的整数

  

x % n的结果是[0,n-1]的一个整数

用do-while循环，因为不管怎么样都要进这个循环，让用户输入这个数



**整数的分解**

对一个整数做%10的操作，就得到它的*个位数*

对一个整数做/10的操作，就去掉了它的十位数

然后再对2的结果做%10，就得到原来数的十位数



**if语句常见的错误**

- 忘了大括号

- if后面不能加分号

- 错误使用==和=

- 使人困惑的else

  在

在if和else之后必须加上大括号形成语句块



# 第五周 循环控制

**break vs continue**

break：跳出循环

continue：跳过循环这一轮剩下的语句进入下一轮

break和continue都只能对它所在的那层循环做

<img src="/Users/draven/Library/Application Support/typora-user-images/image-20210320211834578.png" alt="image-20210320211834578" style="zoom:50%;" />

接力break（int exit = 0)

<img src="/Users/draven/Library/Application Support/typora-user-images/image-20210320213554609.png" alt="image-20210320213554609" style="zoom:33%;" />

**正序分解整数**

- 输入一个非负整数，正序输出它的每一位数字

- 输入：13425

- 输出：1 3 4 2 5 

  

# 第六周 数组

变量可以用来存放数组

**定义数组**

- <类型> 变量名称[元素数量];
- int grades[100];
- double weight[20];
- 元素数量必须是整数
- 数组的下标从0开始

int a[10]

一个int的数组，有10个单元：a[0],a[1],...,a[9]。可以出现在赋值的左边或右边

a[2] = a[1] + 6;（在赋值左边的叫作左值）

注意数组下标不能越界

## 6.2 函数的定义与使用

函数是一块代码，接受零个或多个参数，做一件事情，并返回零个或一个值

<img src="/Users/draven/Library/Application Support/typora-user-images/image-20210321204356011.png" alt="image-20210321204356011" style="zoom: 50%;" />

**调用函数**

- 函数名（）
- （）起到了表示函数调用的重要作用
- 即使没有参数也需要（）

- 如果有参数，则需要给出正确的数量和顺序
- 这些值会被按照顺序依次用来初始化函数中的参数
- 函数直到每一次是哪里调用它，会返回到正确的地方

## 6.3 从函数中返回值

```c
int max(int a, int b)
{
  int ret;
  if (a>b)	{
    ret = a;
  } else {
    ret = b;
  }
  
  return ret;
}
```

- return停止函数的执行，并送回一个值

- return;

- return表达式

- 一个函数里可以出现多个return语句

- 可以赋值给变量，可以再传递给函数

- 甚至可以丢弃

  

**没有返回值的函数**

- void 函数名（参数表）
- 不能使用带值得return
- 可以没有return
- 调用的时候不能做返回值的赋值

**函数先后关系**

- 在看到sum(1,10)的时候，它需要知道sum( )的样子

<img src="/Users/draven/Library/Application Support/typora-user-images/image-20210321211833572.png" alt="image-20210321211833572" style="zoom:33%;" />

- 函数的类型是可以不写参数的名字的

  

**调用函数**

- 如果函数由参数，调用函数时必须传递给它数量、类型正确的值

- 可以传递给函数的值是表达式的结果，这包括：

  字面量

  变量

  函数的返回值

  计算的结果

  

**传值**

过去，对于函数参数表中的参数，叫做“形式参数”，调用函数时给的值，叫做“实际参数”

我们认为，它们是参数和值的关系

<img src="/Users/draven/Library/Application Support/typora-user-images/image-20210321213419099.png" alt="image-20210321213419099" style="zoom: 50%;" />



## 6.3	本地变量

- 函数的每次运行，就产生了一个独立的变量空间，在这个空间中的变量，是函数的这次运行所独有的，称作本地变量

- 定义在函数内部的变量就是本地变量

- 参数也是本地变量

- 本地变量是定义在块内的，可以是定义在函数的块内，也可以定义在语句的块内，甚至可以随便拉一对大括号来定义变量

- 程序运行进入这个块之前，其中的变量不存在，离开这个块，其中的变量就消失了

- 块外面定义的变量在里面仍然有效

- 块里面定义了和外面同名的变量则掩盖了外面的

- 不能在一个块内定义同名的变量

  

**函数没有参数时**

- void f(void)：如果写了void，则表示这个函数不接收任何的参数	***适用于确定函数没有参数的情况***
- void f()：表示参数未知，并不代表没有参数

f(a,b)     -> 传了2个函数进去

f((a,b))    ->传了1个函数进去



C语言不允许函数嵌套定义

**关于main**

- int main()也是一个函数

  

<img src="/Users/draven/Library/Application Support/typora-user-images/image-20210321220727290.png" alt="image-20210321220727290" style="zoom: 50%;" />

<img src="/Users/draven/Library/Application Support/typora-user-images/image-20210321220810945.png" alt="image-20210321220810945" style="zoom:50%;" />

<img src="/Users/draven/Library/Application Support/typora-user-images/image-20210321220830989.png" alt="image-20210321220830989" style="zoom:50%;" />

<img src="/Users/draven/Library/Application Support/typora-user-images/image-20210321220846622.png" alt="image-20210321220846622" style="zoom: 50%;" />

