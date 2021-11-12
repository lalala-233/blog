---
title: C++ 字符串和字符数组的长度
date: 2021-10-31 13:37:00
tags:
- C++
categories:
- [Author, 该名字被和谐了]
- [编程, C++]
---

&emsp;&emsp;我居然鸽了这么久，还不小心发出了空白的页面……

---

&emsp;&emsp;突发奇想，想做个根据指定指令做出回应的程序。
&emsp;&emsp;其中一项便是返回错误。
&emsp;&emsp;当时的思路是：当字符数组的长度达到一定长度时，清空数组并返回 Error。
&emsp;&emsp;上网搜了一些资料，写出来了。
&emsp;&emsp;本人是初学者，代码中写的不好的地方麻烦指出，谢谢。（邮箱：2317987274@qq.com）
&emsp;&emsp;代码如下：
```C++
//用字符数组。

#include <iostream>

using namespace std;

int main()
{
	short Length = 0;    //字符串长度。
	short Sizeof;        //字符串大小。
	short MLength = 0;   //规定输入的最大长度。
	cout << "Please enter the maximum length of the char[]: ";
	cin >> MLength;
	char Input[MLength] = {};   //输入。
	while(true)
	{
		system("cls");
		Length = strlen(Input);
		Sizeof = sizeof(Input);
		if ( Length > MLength )
		{
			strcpy(Input, "Error!");   //重置信息。
		}
		cout
		<< "Input is: " << Input << endl
		<< "Length is: " << Length << endl
		<< "Sizeof is: " << Sizeof << endl
		<< "Please enter the value of char[]: ";   //输出信息。
		cin >> Input;
	}
}
```
&emsp;&emsp;还有一种：
```C++
//用字符串。
#include <iostream>

using namespace std;

int main()
{
	short Length = 0;    //Length2 =字符串长度。
	short Sizeof;        //字符串大小。
	short MLength = 0;   //规定输入的最大长度。
	cout << "Please enter the maximum length of the string: ";
	cin >> MLength;
	string Input;        //输入。
	while(true)
	{
		system("cls");
		Length = Input.size();
		Sizeof = sizeof(Input);
		if ( Length > MLength )
		{
			Input = "Error!";   //重置信息。
		}
		cout
		<< "Input is: " << Input << endl
		<< "Length is: " << Length << endl
		<< "Sizeof is: " << Sizeof << endl
		<< "Please enter the value of string: ";   //输出信息。
		cin >> Input;
	}
}
```
&emsp;&emsp;简单来说就是无限循环，每循环一次就清空一次控制台信息，并自动获取代码的长度和大小并输出。
&emsp;&emsp;这也算是间接的学了学 "sizeof()"、".size()"、"strlen" 等关键字的用法吧。
&emsp;&emsp;所有代码均在「Win7 64 位」成功运行。

