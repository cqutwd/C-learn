### 储存类：

##### static：静态变量在全局数据区分配内存而非栈

##### 修饰变量叫静态变量，未赋值自动初始化为0，在函数中只会被定义一次，只能在定义的函数内操作，不会随着函数的结束而被释放，随程序结束释放

##### 修饰全局变量时：只能在本文件中调用，即便是extern外部申明也不可以

##### 修饰函数时，也只能在本文件中调用。

### 位运算符：

##### &：同位逻辑与

##### |：同位逻辑或

##### ^：同位逻辑异或

##### ~：整体翻转

##### <<,>>:逻辑左右移位，a << 2

### cmath函数和随机数生成：

##### 参考[C++ 数字_w3cschool](https://www.w3cschool.cn/cpp/cpp-numbers.html)

![image-20240819094520297](C:\Users\王东\AppData\Roaming\Typora\typora-user-images\image-20240819094520297.png)

```c++
#include<iostream>
#include<ctime>
#include<cstdlib>
using namespace std;
int main(){
    int i,j;
    //设置种子
    srand( (unsigned)time(NULL) );
    //生成10个随机数
    for( i = 0; i < 10; i ++){
        j = rand();
        cout << "随机数： " << j << endl;
    }
    return 0;
}
```

### 数组：

##### C++不允许向函数传递一个完整的数组作为参数，但是可以传递指向数组的指针

##### 参考：[详谈C++中数组作为函数参数_c++数组作为函数参数-CSDN博客](https://blog.csdn.net/huangyimo/article/details/80051192)

```c++
//如果我们传给print函数以一个数组，则实参自动转换成指向数组首元素的指针，数组大小对函数的调用没有影响
//尽管形式不同，但这三个print函数是等价的
//每个函数都有一个const int*类型的形参
void print(const int *);
void print(const int[]);
void print(const int[10]);//传入的数组大小可以不为10;
int i = 0, j[2] = {1,2};
print(&i);//正确：&i转换成int*
print(j);//正确：j为int*类型，指向j[0]
```

### 字符串：

##### string类：简化了字符串的复制，连接，求长度的方法

```c++
#include<iostream>
#include<cstring>

using namespace std;
int main(){
    string str1 = "Hello,world";
    string str2 = "Hello,Linux";
    string str3;
    int len;
    //复制str1到str3
    str3 = str1;
    cout << "str3: " << str3 << endl;
    
    //连接str2和str1
    str3 = str1 + str2;
    cout << "str1 + str2: " << str3 << endl;
    
    //连接后，str3的总长度
 	len = str3.size();
    cout << "str3.size(): " << len << endl;
    return 0;
}
```

