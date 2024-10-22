## 指针和引用
、、、
int a=5;
int &b=a;  //初始化b的地址等于a的地址，b为int类型，&b为地址类型
int *p = &a; //&a等于a的地址，初始化时p为指针类型
cout<<*p<<endl; //p指向地址的值
cout<<&a<<endl; //a的地址
cout<<p<<endl; //p指向的地址 也是a的地址
cout<<&p<<endl; //p的地址，另一个地址
、、、
## const
方法 去掉对象名倒着读
+ 指针
  + 指向常量的指针 `const int* p`const在数据类型前面
  + 自身的常量的指针 `int* const p`const在数据类型后面，数据前面，
+ 引用
  + 指向常量的引用 `const int &q=a` 只有这一种，此时q的值不能改变，a的值可以改变
