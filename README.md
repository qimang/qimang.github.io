# 欢迎来到齐芒的博客
> **一盏灯， 一片昏黄； 一简书， 一杯淡茶。 守着那一份淡定， 品读属于自己的寂寞。 保持淡定， 才能欣赏到最美丽的风景！ **

>>齐芒行，川锋明！
----
![](https://cdn.luogu.com.cn/upload/image_hosting/a5tc02q3.png)
![](https://cdn.luogu.com.cn/upload/image_hosting/zx1q0ua3.png)
![yesOrNo](https://img-blog.csdn.net/20160722143450018)

###此博客主要用来记录我的算法学习（权当笔记）
                            ```如有不足，敬请大佬指正```
### 目录



---
1.[st表](https://paste.ubuntu.com/p/WvGHYX45Fm/)

```
#include <bits/stdc++.h>
#define ll int 
using namespace std;
const int maxn=1e5+7;
int n;
int M[maxn][1050];
void st_RMQ()
{
    for (int j=1;(1<<j)<=n;++j)
      for (int i=0;i+(1<<j)-1<=n;++i)
         M[i][j]=max(M[i][j-1],M[i+(1<<(j-1))][j-1]);

}
int RMQ(int l,int r)
{
    int k=0;
    while ((1<<(k+1))<=r-l+1) ++k;
    return max(M[l][k],M[r-(1<<k)+1][k]);
}
int main()
{
  int t;
  cin>>n>>t;
  for (int i=1;i<=n;++i)
     cin>>M[i][0];///以i开头长度为1中的最大值
  st_RMQ();
  int x,y;
  while(t--)
  {
     scanf("%d%d",&x,&y);
     printf("%d\n",RMQ(x,y));
  }
  return 0;
}
```
