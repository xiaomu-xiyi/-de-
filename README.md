# -de-
//#include<stdio.h>
//#include<string.h>
////int main()
//{
//	char password[20] = { 0 };
//	int i = 0;
//	for (i = 0; 1 < 3; i++)
//	{
//		printf("请输入密码:>");
//		scanf_s("%s", password);
//		if (strcmp(password, "123456"))
//		{
//			printf("密码正确\n");
//			break;
//		}
//		else
//			printf("密码错误\n");
//	}
//	if (i == 3)
//		printf("密码错误\n");
//	return 0;
//}
//#include<stdio.h>
////int Add(int x, int y)
//{
//	int z = 0;
//	z = x + y;
//	return z;
//}
//////int main()
//{
//	int sum = 0;
//	int a = 10;
//	int b = 20;
//	sum = Add(a, b);
//	printf("%d\n", sum);
//	return 0;
//}
//#include<string.h>
//#include<stdio.h>
//////int main()
//{
//	char arr1[] = "bit";
//	char arr2[] = "##############";
//	strcpy_s(arr2, arr1);
//	printf("%s\n", arr2);
//	return 0;//}//#include<string.h>
//#include<stdio.h>
////int main()
//{
//	char arr1[] = "hello world";
//	memset(arr1, '*', 5);
//	printf("%s", arr1);
//	return 0;
//}
//#include<stdio.h>
//////void Swap1(int x, int y)
////{
////	int tem = 0;
////	tem = x;
////	x = y;
////	y = tem;
////}
//void Swap(int* pa, int* pb)
//{
//	int tem = 0;
//	tem = *pa;
//	*pa = *pb;
//	*pb = tem;
//}
////int main()
//{
//	int a = 10;
//	int b = 20;
//	printf("a = %d b = %d\n", a, b);
//	
//Swap1(a, b);
//	Swap(&a, &b);
//	printf("a = %d b = %d\n", a, b);
////	return 0;
//}
//打印素数（100--200）
//#include<stdio.h>
////int is_prime(int x)
//{
//	int a =0;
//	for (a = 2; a < x; a++)
//	{
//		if (x%a == 0)
//			return 0;
//	}
//	return 1;
//}
//////int main()
//{
//	int i = 0;
//	for (i = 100; i <= 200; i++)
//	{
//		if (is_prime(i) == 1)
//		printf("%d\n", i);
//	}
//	return 0;
//打印1000--2000年的闰年
#include<stdio.h>

int is_leap_year(int y)
{
	if (y % 4 == 0 && y % 100 != 0 || y % 400 == 0)
		return 1;
	else
		return 0;
}

int main()
{
	int year = 0;
	for (year = 1000; year <= 2000; year++)
	{
		if (is_leap_year(year) == 1)
			printf("%d\n", year);
	}

	return 0;
}

//从12345678910中找到7
//普通方法
#include<stdio.h>

int main()
{
	int arr[] = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };
	int k = 11;
	int left = 0;
	int sz = sizeof(arr) / sizeof(arr[0]);
	int right = sz - 1;
	while (left<=right)
	{
		int mid = (left + right) / 2;
		if (mid < k)
		{
			left = mid + 1;
		}
		else if (mid>k)
		{
			right = mid - 1;
		}
		else
		{
			printf("找到了，下标是%d\n", mid);
			break;
		}
	}
	if (left > right)
		printf("找不到\n");
	return 0;
}



//函数法
#include<stdio.h>

//int binary_search(int arr1[], int a)//这里的arr传过来的是数组的首元素地址

int binary_search(int arr[], int a, int sz)
{
	//int sz = 9;
	int left = 0;
	int right = sz - 1;
	while (left <= right)
	{
		int mid = (left + right) / 2;
		if (arr[mid] < a)
		{
			left = mid + 1;
		}
		else if (arr[mid]>a)
		{
			right = mid - 1;
		}
		else
		{
			return mid;
			break;
		}
	}
	if (left > right)
		return -1;
}

int main()
{
	int arr[] = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };
	int k = 7;
	int sz = sizeof(arr) / sizeof(arr[0]);
	int ret = binary_search(arr, k, sz);
	if (ret == -1)
	{
		printf("找不到\n");
	}
	else
	{
		printf("找到了，它的下标是%d\n", ret);
	}

	return 0;
}
#include<stdio.h>

void Add(int* p)
{
	(*p)++;
}

int main()
{
	int num = 0;
	Add(&num);
	printf("%d\n", num);
	Add(&num);
	printf("%d\n", num);
	Add(&num);
	printf("%d\n", num);
	Add(&num);
	printf("%d\n", num);
	return 0;
}
//#include<stdio.h>
//
//int main()
//{
//	printf("%d", printf("%d", printf("%d", 43)));
//	//printf()的返回值是打印字符的个数。
//
//	return 0;
//}

////函数递归（栈溢出）
//#include<stdio.h>
//
//int main()
//{
//	printf("hehe\n");
//		main();
//	return 0;
//}

//递归例题
//将1234 打印为1 2 3 4
//
//
//
//#include<stdio.h>
//
//void print(int x)
//{
//	if (x > 9)
//	{
//		print(x / 10);
//	}
//	//这里不能加else，否则只有最高位数字进来
//		printf("%d ", x%10);
//}
//int main()
//{
//	unsigned int num = 0;
//	scanf_s("%d", &num);
//	print(num);
//	return 0;
//}


////用函数计算字符长度（创建临时变量的方法）
//#include <stdio.h>
//
//int my_strlen(char* str)
//{
//	int count = 0;
//	while (*str != '\0')
//	{
//		str++;
//		count++;
//	}
//	return count;
//}
//
//
//
//int main()
//{
//	char arr[] = "zxcvcbb";
//	int len = my_strlen(arr);
//		printf("len = %d\n", len);
//	return 0;
//}


////用递归的办法求字符长度（不用创建临时变量）
//
//#include <stdio.h>
//
//int my_strlen(char *str)
//{
//	if ((*str) != '\0')
//	{
//		return (1 + my_strlen(str + 1));
//	}
//	else
//		return 0;
//}
//
//int main()
//{
//	char arr[] = "zcjfshudigrhugrehgrhgushgr";
//	int len = my_strlen(arr);
//	printf("字符串的长度为 %d\n", len);
//	return 0;
//}

//求n 的阶乘
//
//#include <stdio.h>
//
//int Fac1(int a)
//{
//	if (a <= 1)
//		return 1;
//	else
//		return a*(Fac1(a - 1));
//}
//int Fac2(int n)
//{
//	int i = 0;
//	int ret = 1;
//	for (i = 1; i <= n; i++)
//	{
//		ret *= i;
//	}
//	return ret;
//}
//
//int main()
//{
//	int n = 0;
//	int ret = 0;
//	int ret2 = 0;
//	scanf_s("%d", &n);
//	ret = Fac1(n);
//	printf("%d\n", ret);
//	ret2 = Fac2(n);
//	printf("%d\n", ret2);
//	return 0;
//}
#define _CRT_SECURE_NO_WARNING 1

#include <stdio.h>

#include <string.h>

//int Add(int x, int y)
//{
//	int z = x + y;
//	return z;
//}
//
//int main()
//{
//	int num1 = 10;
//	int num2 = 20;
//	int a = 1;
//	int b = 2;
//	int sum = 0;
//
//	sum = Add(a, b);
//	printf("%d\n", sum);
//	return 0;
//
//}
//
//
//
//#include<stdio.h>
//
//int main()
//{
//	int arr[] = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 0 };
//	int sz = sizeof(arr) / sizeof(arr[0]);
//	int i = 0;
//	for (i = 0; i < sz; i++)
//	{
//		printf("&arr[] = %p\n", &arr[i]);
//	}
//	return 0;
//}
//
//#include <stdio.h>
//
//int main()
//{
//	int arr[3][4] = { 1, 2.3, 4, 5 };
//	printf("%d", arr);
//	return 0;
//}


#include <stdio.h>

int main()
{
	int arr[4][4] = { 1, 2, 3, 4, 5, 6, 7, 8 };
	int i = 0;
	for (i = 0; i < 4; i++)
	{
		int j = 0;
		for (j = 0; j < 4; j++)
		{
			printf("%d ", arr[i][j]);
		}
		printf("\n");
	}
	return 0;
}

#include<stdio.h>

void bubble_sort(int arr[], int sz)
{
	int i = 0;
	for (i = 0; i < sz - 1; i++)
	{
		int flag = 1;
		int j = 0;
		for (j = 0; j < sz - 1 - i; j++)
		{
			if (arr[j]>arr[j + i])
			{
				int tmp = arr[j];
				arr[j] = arr[j + 1];
				arr[j + 1] = tmp;
				flag = 0;
			}
		}
		if (flag == 1)
		{
			break;
		}
	}

}
int main()
{
	int arr[] = {1,2,3,4,5,6,7,8,9};
	int i = 0;
	int sz = sizeof(arr) / sizeof(arr[0]);
	bubble_sort(arr, sz);
	for (i = 0; i < sz; i++)
	{
		printf("%d ", arr[i]);
	}
	return 0;
}
