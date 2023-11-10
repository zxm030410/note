#  算法(algorithm)

##  排序算法

###  算法时间复杂度

![20210316213527859](C:\Users\meng\Desktop\20210316213527859.png)

####  快速排序

```

```

####  归并排序
```c++
#include<iostream>
#define fastio std::ios::sync_with_stdio(false),std::cin.tie(0);
const int N = 1e6+10;
int q[N] ,temp[N];

void merge_sort(int q[],int l,int r)
{
    if( l>=r )return;
    int mid = l + r >> 1;
    merge_sort(q,l,mid),merge_sort(q,mid+1,r);
    
    int k = 0 ,i = l,j = mid+1;
    while(i<=mid&&j<=r)
    {
        if(q[i]<=q[j]) temp[k++] = q[i++];
        else temp[k++] = q[j++];
    }
    while(i<=mid) temp[k++] = q[i++];
    while(j<=r) temp[k++] = q[j++];
    
    for(int i =0,j = l;j<=r;j++,i++)
    {
        q[j] = temp[i]; 
    }
}
int main()
{
    fastio;
    int n;
    std::cin>>n;
    for(int i = 0 ;i<n;i++) std::cin>>q[i];
    
    merge_sort(q,0,n-1);
    for(int i=0;i<n;i++) std::cout<<q[i]<<" ";
    
    return 0;
 }
```
####  归并排序求逆序对
<p align = "left" >
给定一个长度为 n 的整数数列，请你计算数列中的逆序对的数量。逆序对的定义如下：对于数列的第 i 个和第 j 个元素，如果满足 i < j 且 a[i]>a[j] ，则其为一个逆序对；否则不是。

## 搜索

###  N皇后问题
![image-20230916225838138](C:\Users\meng\AppData\Roaming\Typora\typora-user-images\image-20230916225838138.png)
```c++
#include<iostream>
#include<cstring>
const int N =20;

char g[N][N];

int n;

bool cols[N],dg[2*N],udg[2*N];

void dfs(int u)
{
    if(u == n)
    {
        for(int i=0;i<n;i++)
            puts(g[i]);
        puts("");
        return ;
    }
    
    for(int i=0;i<n;i++)
    {
        if(!cols[i]&&!dg[u+i]&&!udg[n-u+i])
        {
            g[u][i]='Q';
            cols[i] = dg[u+i] = udg[n-u+i] = true;
            dfs(u+1);
            cols[i] = dg[u+i] = udg[n-u+i] = false;
            g[u][i] = '.';
        }
    }
}

int main()
{

    std::cin>>n;
    
   for(int i=0;i<n;i++)
   {
       for(int j=0;j<n;j++)
       {
           g[i][j]='.';
       }
   }
    
    dfs(0);
    
    return 0;
}
```
####  不同路径数

![image-20230917194609456](C:\Users\meng\AppData\Roaming\Typora\typora-user-images\image-20230917194609456.png)

```c++
#include<iostream>
#include<unordered_set>
#include<string>
int n,m,k;
const int N = 10;
std::unordered_set<std::string>ans;
char g[N][N];
void dfs(int x,int y,int u,std::string path)
{
    if( u == k+1)
    {
        ans.insert(path); //结果存入 set 并去重
        return ; //要记得return 不然会MLE
    }
    int dx[]{0,0,1,-1},dy[]{1,-1,0,0}; //偏移量   
    for(int i=0;i<4;i++)  //上下左右走
    {
        int a = x+dx[i] , b = y +dy[i];
        if(a<n&&a>=0&&b<m&&b>=0) //不出边界
        dfs(a,b,u+1,path+g[a][b]);
    }
}
int main()
{
    std::cin>>n>>m>>k;
    std::string res; //用来存每次的结果
    for(int i =0;i<n;i++)
    {
        for(int j = 0;j<m;j++)
        {
            std::cin>>g[i][j];
        }
    } 
    for(int i=0;i<n;i++)
    {
        for(int j=0;j<m;j++)
        {
            dfs(i,j,0,res); //每个点都遍历一遍
        }
    }
    std::cout<<ans.size();
    return 0;
}
```



####   迷宫

#####  题目描述

给定一个  N &times; M   方格的迷宫，迷宫里有  T  处障碍，障碍处不可通过。

在迷宫中移动有上下左右四种方式，每次只能移动一个方格。数据保证起点上没有障碍。

给定起点坐标和终点坐标，每个方格最多经过一次，问有多少种从起点坐标到终点坐标的方案。

######  输入格式

第一行为三个正整数  N,M,T ，分别表示迷宫的长宽和障碍总数。

第二行为四个正整数 SX,SY,FX,FY，SX , SY   代表起点坐标，FX , FY  代表终点坐标。

接下来  T  行，每行两个正整数，表示障碍点的坐标。

######  输出格式

输出从起点坐标到终点坐标的方案总数。

###### 样例 #1

###### 样例输入 #1

```
2 2 1
1 1 2 2
1 2
```

###### 样例输出 #1

```
1
```



```c++
#include<iostream>
#include<algorithm>
#include<cmath>
#include<cstring>
const int N  = 15;

int g[N][N];
bool st[N][N];    

int dx[]{1,-1,0,0},dy[]{0,0,1,-1};
int res;
int n ,m ,t , sx , sy , fx , fy ;  

void dfs(int x,int y)
{
	if(x==fx&&y==fy)  // 记录答案
	{
		res++;
		return ;
	}	
	for(int i=0;i<4;i++)
	{
		int a = x + dx[i] , b = y + dy[i];
		if(st[a][b]==0&&g[a][b]==1)  // 未走过 和 没有障碍
		{
			st[a][b] = 1;  
			dfs(a,b);
			st[a][b] = 0; 
		}
	}
}

int main()
{
	std::cin>>n>>m>>t>>sx>>sy>>fx>>fy;

	
	for(int i =1 ;i<=n;i++)
	{
		for(int j=1;j<=m;j++)
		{
			g[i][j] = 1;  // 初始化地图 1 表示为走过
		}
	}

    st[sx][sy] = true;  //标记起点位置 不然会重复访问起点

	while(t--)  // 存入障碍
	{
		int l,r;
		std::cin>>l>>r;
		g[l][r] = 0;   // 0 表示障碍
	}

	dfs(sx,sy);

	std::cout<<res;

	return 0;
}
```


#### 自然数的拆分问题

#####  题目描述

任何一个大于 1 的自然数  n ，总可以拆分成若干个小于  n  的自然数之和。现在给你一个自然数  n ，要求你求出  n  的拆分成一些数字的和。每个拆分后的序列中的数字从小到大排序。然后你需要输出这些序列，其中字典序小的序列需要优先输出。

###### 输入格式

输入：待拆分的自然数 n。

###### 输出格式

输出：若干数的加法式子。

###### 样例 #1

###### 样例输入 #1

```
7
```

###### 样例输出 #1

```
1+1+1+1+1+1+1
1+1+1+1+1+2
1+1+1+1+3
1+1+1+2+2
1+1+1+4
1+1+2+3
1+1+5
1+2+2+2
1+2+4
1+3+3
1+6
2+2+3
2+5
3+4
```

```c++
#include<iostream>
const int N = 10;
int q[N];
int n;
void dfs(int x,int sum,int t)   // x 表示从当前数开始选择 ，sum 表示求和 ，t 表示 所选数
{
	if(x == n) return ; // 防止当前数为 n 直接输出
	if(sum == n)
	{
		for(int i=0;i<t-1;i++)
		{
			std::cout<<q[i]<<"+";
		}
		std::cout<<q[t-1];
		puts("");
		return ;
	}
	for(int i=x;i<=n-sum;i++)
	{
		q[t] = i;
		dfs(i,sum+i,t+1);
	}
}
int main()
{
	std::cin>>n;
	dfs(1,0,0);
	return 0;
}
```

####  BFS(acwing - 844 走迷宫)
```c++
#include<iostream>
#include<queue>
#include<cstring>
int n,m;
typedef std::pair<int ,int> PII;
int dx[]{1,-1,0,0},dy[]{0,0,1,-1};
const int N = 110;
int g[N][N];  //存放地图
int d[N][N];  //终点到起点的距离

int bfs()
{
	memset(d,-1,sizeof d); // d数组初始化为-1 ，表示还未走
	std::queue<PII>q;
	q.push({0,0});  // 放入起点位置

	d[0][0] = 0;
	while(q.size()) //队列不为空
	{
		PII t = q.front(); // 取出对头；
		q.pop(); // 出队

		for(int i=0;i<4;i++)
		{
			int x = t.first + dx[i] , y = t.second + dy[i];
			if(x>=0&&x<n&&y>=0&&y<m&&g[x][y]==0&&d[x][y]==-1)
			{
				d[x][y] = d[t.first][t.second]+1; //当前点到起点的距离加1
				q.push({x,y}); // 将新的点存入队列中
			}
		}
	}

	return d[n-1][m-1]; 
}

int main()
{
	std::cin>>n>>m;
	for(int i=0;i<n;i++)
	{
		for(int j = 0;j<m;j++)
		{
			std::cin>>g[i][j];
		}
	}
	std::cout<<bfs();
	return 0;
}
```
##### 马的遍历

######  题目描述

有一个 n * m 的棋盘，在某个点 $(x, y)$ 上有一个马，要求你计算出马到达棋盘上任意一个点最少要走几步。

###### 输入格式

输入只有一行四个整数，分别为 n, m, x, y。

###### 输出格式

一个 n * m 的矩阵，代表马到达某个点最少要走几步（不能到达则输出 -1）。

###### 样例 #1

###### 样例输入 #1

```
3 3 1 1
```

###### 样例输出 #1

```
0    3    2    
3    -1   1    
2    1    4
```

```c++
#include<iostream>
#include<cstring>
#include<queue>
int n,m,x,y;
const int N = 410;
int d[N][N];  // 记录走路的步数
bool st[N][N]; // 存储当前点是否走过
int dx[] = {-1, 1, -2, -2, -1, 1, 2, 2};  //八个方向 代表 马走日
int dy[] = {-2, -2, -1, 1, 2, 2, -1, 1};  //用向量的表示方式
typedef std::pair<int ,int> PII;

void bfs()
{
	memset(d,-1,sizeof d);

	st[x][y] = true;  //表示已近走过
	std::queue<PII> q;

	q.push({x,y});

	d[x][y] =0;
	while(q.size())
	{
		PII t = q.front();
		q.pop();
		for(int i =0 ;i<8;i++)
		{
			int a = t.first + dx[i] , b = t.second + dy[i];
			if(a<=n&&a>=1&&b<=m&&b>=1&&st[a][b]==0)  // 判断边界问题以及是否走过这一点
			{
				st[a][b] = true;
				d[a][b] = d[t.first][t.second]+1;
				q.push({a,b});
			}
		}
	}

}
int main()
{
	std::cin>>n>>m>>x>>y;
	bfs();

	for(int i=1;i<=n;i++)
	{
		for(int j=1;j<=m;j++)
		{
			printf("%-5d",d[i][j]);
		}
		puts("");
	}
	return 0;
}
```
##  动态规划
###  01背包问题
```c++
二维
#include <iostream>
#include <cstring>
#include <algorithm>
const int N = 1010;
int n,m;
int f[N][N];
int v[N],w[N];
int main()
{
    std::cin>>n>>m;
    for(int i=1;i<=n;i++) std::cin>>v[i]>>w[i];
    for(int i=1;i<=n;i++)
    {
        for(int j=0;j<=m;j++)
        {
            f[i][j] = f[i-1][j];
            if(j>=v[i])
            f[i][j] = std::max(f[i-1][j],f[i-1][j-v[i]]+w[i]);
        }
    }
    std::cout<<f[n][m];
    return 0;
}

一维优化(滚动数组) 节约空间



```

