### 第一个C语言程序

```c
# include <stdio.h> 	// 引入头文件
int main(void) {		// 函数
    int number = 10;	// 变量声明及赋值
    printf("当前的number是%d\n", number);	// 输出语句
    return 0;			// 函数返回
}
```

### 基本数据类型

C语言的基本数据类型为：整型、字符型、实数型。这些类型按其在计算机中的存储方式可被分为两个系列，即整数(integer)类型和浮点数(floating-point)类型。 
这三种类型之下分别是：short、int、long、char、float、double 这六个关键字再加上两个符号说明符signed和unsigned就基本表示了C语言的最常用的数据类型。 
下面列出了在32位操作系统下 常见编译器下的数据类型大小及表示的数据范围：

| 类型名称       | 占字节数 | 其他叫法           | 表示的数据范围                 |
| -------------- | -------- | ------------------ | ------------------------------ |
| char           | 1        | signed char        | -128 ~ 127                     |
| unsigned char  | 1        | none               | 0 ~ 255                        |
| int            | 4        | signed int         | -2,147,483,648 ~ 2,147,483,647 |
| unsigned int   | 4        | unsigned           | 0 ~ 4,294,967,295              |
| short          | 2        | short int          | -32,768 ~ 32,767               |
| unsigned short | 2        | unsigned short int | 0 ~ 65,535                     |
| long           | 4        | long int           | -2,147,483,648 ~ 2,147,483,647 |
| unsigned long  | 4        | unsigned long      | 0 ~ 4,294,967,295              |
| float          | 4        | none               | 3.4E +/- 38 (7 digits)         |
| double         | 8        | none               | 1.7E +/- 308 (15 digits)       |
| long double    | 10       | none               | 1.2E +/- 4932 (19 digits)      |



### 关键字

| C语言中的32个关键字 |        |          |          |
| ------------------- | ------ | -------- | -------- |
| auto                | double | int      | struct   |
| break               | else   | long     | switch   |
| case                | enum   | register | typedef  |
| char                | extern | return   | union    |
| const               | float  | short    | unsigned |
| continue            | for    | signed   | void     |
| default             | goto   | sizeof   | volatile |
| do                  | if     | static   | while    |



### 基本输入输出函数

#### 字符输出函数putchar

putchar函数是字符输出函数，其功能是在终端（显示器）输出单个字符。其一般调用形式为： 
putchar(字符变量); 
例: 

```c
`putchar``(‘A’); ``/*输出大写字母A */``putchar``(x);  ``/*输出字符变量x的值*/``putchar``(‘\n’); ``/*换行*/`
```

#### 字符输入函数getchar

getchar函数的功能是接收用户从键盘上输入的一个字符。其一般调用形式为： 
getchar(); 
getchar会以返回值的形式返回接收到的字符.通常的用法如下: 

```c
`char` `c;  ``/*定义字符变量c*/``c=``getchar``(); ``/*将读取的字符赋值给字符变量c*/`
```

#### 格式化输出函数printf

printf函数叫做格式输出函数，其功能是按照用户指定的格式，把指定的数据输出到屏幕上

printf函数的格式为: 

printf(“格式控制字符串”,输出表项);   

常用的输出格式及含义如下:

| 格式字符 |                                                    |
| -------- | -------------------------------------------------- |
| d , i    | 以十进制形式输出有符号整数(正数不输出符号)         |
| O        | 以八进制形式输出无符号整数(不输出前缀0)            |
| x        | 以十六进制形式输出无符号整数(不输出前缀0x)         |
| U        | 以十进制形式输出无符号整数                         |
| f        | 以小数形式输出单、双精度类型实数                   |
| e        | 以指数形式输出单、双精度实数                       |
| g        | 以%f或%e中较短输出宽度的一种格式输出单、双精度实数 |
| C        | 输出单个字符                                       |
| S        | 输出字符串                                         |

#### 格式化输入函数scanf

scanf函数称为格式输入函数，即按照格式字符串的格式，从键盘上把数据输入到指定的变量之中。Scanf函数的调用的一般形式为： 
scanf(“格式控制字符串”，输入项地址列表); 
其中，格式控制字符串的作用与printf函数相同，但不能显示非格式字符串，也就是不能显示提示字符串。地址表项中的地址给出各变量的地址，地址是由地址运算符”&”后跟变量名组成的。 
Scanf 函数中格式字符串的构成与printf函数基本相同，但使用时有几点不同. 
(1) 格式说明符中，可以指定数据的宽度，但不能指定数据的精度。例： 

```c
`float` `a；``scanf``(“%10f”，&a);  ``//正确``scanf``(“%10.2f”,&a); ``//错误`
```

(2) 输入long类型数据时必须使用%ld，输入double数据必须使用%lf或%le。 
(3) 附加格式说明符”*”使对应的输入数据不赋给相应的变量。 

*修饰符在scanf中()的用法：
*在scanf()中提供截然不同的服务，当把它放在%和说明符字母之间时，它使函数跳过相应的输入项目。

关于scanf()的返回值
scanf() 函数返回成功读入的项目的个数。如果它没有读取任何项目(比如它期望接收一个数字而您却输入的一个非数字字符时就会发生这种情况),scanf()返回0。 
当它检测到“文件末尾”(end of file)时，它返回EOF(EOF在是文件stdio.h中的定义好的一个特殊值，一般，#define指令将EOF的值定义为-1)。