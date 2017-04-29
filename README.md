#include <iostream>
#include <iomanip>
#include <cmath>
using namespace std;
#define N 6
int i,j,b,k=0;
int isprime (int m)
{
	int i;
	double k;
	k=sqrt((double)m);
	for (i=2;i<=(int)k;i++)
		if ((int)m%i==0) break;
	if (i>k) return 1;
		else return 0;
}
int main()
{
	int a[N][N];
	cout <<"请以行的方式输入一个"<<N<<"阶矩阵: \n";
	for(int i=0;i<N;i++)
	{for (int j=0;j<N;j++)
	cin >> a[i][j];}
	cout <<"该矩阵为：\n";
	for (i=0;i<N;i++)
	{for (j=0;j<N;j++)
		{cout <<setw(4)<<a[i][j];
			if (j==N-1)
			cout <<"\n";}
	}
		cout <<"\n";
		cout <<"该矩阵对角线上元素为素数的是：\n";
		for (i=0;i<N;i++)
		{
			j=i;
			b=isprime(a[i][j]);
			if (b)
			{cout <<setw(4)<< a[i][j];
			k++;}
			else 
				continue;
		}
		cout <<"共有：";
		cout <<k<<"个";
		k=0;
		cout <<"\n";
		cout <<"该矩阵反对角线元素为素数的是：\n";
		for (i=0;i<N;i++)
		{j=N-1-i;
		b=isprime(a[i][j]);
		if (b)
		{cout<<setw(4)<<a[i][j];
		k++;}
		else 
			continue;
		}
		cout <<"共有：";
		cout <<k<<"个";
		return 0;
}
