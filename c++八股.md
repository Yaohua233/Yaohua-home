## 指针和引用
```c++
int a=5;
int &b=a;  //初始化b的地址等于a的地址，b为int类型，&b为地址类型
int *p = &a; //&a等于a的地址，初始化时p为指针类型
cout<<*p<<endl; //p指向地址的值
cout<<&a<<endl; //a的地址
cout<<p<<endl; //p指向的地址 也是a的地址
cout<<&p<<endl; //p的地址，另一个地址
```
## const
方法 去掉对象名倒着读
+ 指针
  + 指向常量的指针 `const int* p`const在数据类型前面
  + 自身的常量的指针 `int* const p`const在数据类型后面，数据前面，
+ 引用
  + 指向常量的引用 `const int &q=a` 只有这一种，此时q的值不能改变，a的值可以改变
## 宏定义#define和const常量
## static
在 C++ 中 static 的内部实现机制：静态数据成员要在程序一开始运行时就必须存在。  
全局静态变量  作用域在声明文件之内
局部静态变量  作用域为函数或语句块
静态函数  仅在声明它的文件中可见
类的静态成员  无论创建多少个类的对象，**静态成员都只有一个副本**，与对象无关，所有对象共享，可以对对象进行计数  
  类名加范围解析运算符 :: 就可以访问
类的静态函数  同 类的静态成员，不能访问类的this指针
## this指针
`this` 指针被隐含地声明为: ` ClassName *const this `  
ClassName 类的 `const` 成员函数中，`this` 指针的类型为：`const ClassName* const`  
## inline内联函数  
相当于把内联函数里面的内容写在调用内联函数处  
## 虚函数和纯虚函数
`virtual void funtion1()=0`  
一个类函数的调用并不是在编译时刻被确定的，而是在运行时刻被确定的  
c++运行时会查看指针指向的实际类型，再决定用哪个函数  
`virtual ReturnType FunctionName(Parameter)`  
**纯虚函数最显著的特征是**：它们必须在继承类中重新声明函数，而且它们在抽象类中往往没有定义。  
## volatile
声明的变量，每次都必须从内存中取出值  
const 可以是 volatile （如只读的状态寄存器）  
指针可以是 volatile  
## assert断言  
一般用在调试的时候 类似if 但是不为真时调用abort  
## sizeof()
sizeof 对数组，得到整个数组所占空间大小。  
sizeof 对指针，得到指针本身所占空间大小。  
## extern
## struct和class
- 最本质的一个区别就是默认的访问控制  
	1. 默认的继承访问权限。struct 是 public 的，class 是 private 的。
	2. struct 作为数据结构的实现体，它默认的数据访问控制是 public 的，而 class 作为对象的实现体，它默认的成员变量访问控制是 private 的。
## union
节省空间的特殊类 相同的内存位置储存不同的数据类型  
- 普通union  
- 全局静态匿名union  
- 局部匿名union  
## 面向对象三大特性
封装、继承、多态  
## explicit
防止隐式转换  
