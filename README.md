# 欢迎来到齐芒的博客
>  **一盏灯， 一片昏黄； 一简书， 一杯淡茶。 守着那一份淡定， 品读属于自己的寂寞。 保持淡定， 才能欣赏到最美丽的风景 .**

> *齐芒行，川锋明！*
----
![](https://cdn.luogu.com.cn/upload/image_hosting/zx1q0ua3.png)

###  此博客主要用来记录我的算法学习（权当笔记）
                            ```如有不足，敬请大佬指正```




---
1.[st表](https://paste.ubuntu.com/p/WvGHYX45Fm/)
   在迅哥的讲解下（说实话没有认真听，不过关系不大）
   本题采用的倍增的思路  （说实话感觉像个dp）
首先令M[i][j]代表从i开始长度为2^j的数列  中的极值(左闭右开的区间）
![](https://upload-images.jianshu.io/upload_images/21992567-801b2d62fbba8376.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
```
由此图可知   找寻极值之时只要查找左右两个区间就行了（有点二分的意味） 所以输入的原始值就是M[i][0]    而每一次找寻的过程中就是M[i][j]=极值(M[i][j-1],M[i+2^(j-1)][j-1])   只要从2^j开始例举，但是注意因为i是从1开始，而最少j=1，所以i的值小于等与n-1，并非n。
```
 ![](https://upload-images.jianshu.io/upload_images/21992567-339df5b3619f1c07.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
拿迅哥原图说话

给定两个下标l，r进行查询，我的k是从0开始的，所以相等时也要再+1，查找从i开始长度为2^k和从r-2^k+1长度为2^k；只不过可以直接求取（ k = (int)( log((double)(r-l+1)) / log(2.0) );）
我的理解若有错误  洛谷私信我

