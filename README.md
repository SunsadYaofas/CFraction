# CFraction
Fraction class  

算是github上的第一个程序吧，花了几个小时实现了fraction类，主要包括分数（正和负）初始化约分显示，以及加减乘除，以及比较操作符的重载。
以下值得注意的点：

整体架构上
对负数时犹豫了稍微一会，开始考虑过单独记录符号位，用了一个symbol，后来设计是将符号表示在分子之上，这样在显示的时候可以很方便。其他操作也很简单。
当然，我没有删除symbol这个私有变量，因为在后续成员函数实现的时候用到了，删除还是很简单的。

一些错误点：
1、类的定义一定要加分号，否则会在构造函数那里提示不能有返回值错误。
2、运算符重载设计成了全局友元函数，并没有设计成方法。使用全局友元函数是为了访问类对象中的私有成员。可以不用GetNum()和Getdemon()函数，等会改。可以参考 http://blog.csdn.net/wangkechuang/article/details/8002752
3、因为形参为const类型，所以只能调用const类型的成员函数
	 常量对象不能调用非常量成员函数
	 非常量对象可以调用常量成员函数
	 在成员函数后面加上const，表示不能改变成员变量的函数，表示这个函数是常成员函数。一般这种用法适用于类的成员函数。
4、c++ 函数参数部分里的 const 修饰使用来 限定函数的传递值参数:
  比如说：void function(const int Var); 中
  const限定传递过来的参数在函数内不可以改变，也就是说不能在函数内对var进行修改，但是可以取它的值进行使用。
5、还是不要用vc6.0吧，真的是会把正确的代码给提示出各种错误，这个程序中的友元函数以及不能自动提示构造函数一让我十分紧张

其他的总之感觉还是在整个类的实现过程中是要不断修改的。
