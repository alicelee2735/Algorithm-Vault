基本上都是数学函数部分，我死了。前面部分为应用类型，后面有排序，stl，结构体，图论函数哈哈哈哈哈
反正都是要背的玩意儿
还有一些自带的好用的函数都在这里。

note to myself later: idk, re-organize them into groups?? 
# 最大公约数
```cpp
int gcd(int a,int b){
    while(a>0&&b>0){
        if(a>b){
            a = a%b;
        }
        else{
            b = b%a;
        }
    }
    return a+b;
}

```

# 最小公倍数
`long long lcm = a*b/gcd(a,b); `
直接使用gcd函数，要开long long

# 查找子串
```cpp
#include<bits/stdc++.h>
using namespace std;
int main()
{
    string s1 = "123";
    string s2 = "23";
    string s3 = "73";
    cout << s1.find(s2) << endl;;
    unsigned int c = s1.find(s3);
    cout << c << endl;
     
}
```

# memset初始化数组，所有数设0
`memset(a,0,sizeof(a));`

# 数组里求最大值，最小值

```cpp
/*
	*max_element(begin,end)
	求最大成员 
	*min_element(begin,end)
	求最小成员 
*/ 
#include<iostream> 
#include<algorithm> 
using namespace std;
int main(){
    int n;
    cin>>n;
	int a[n];
	for(int i=0;i<n;i++)cin>>a[i];
	cout << *max_element(a,a+n);
} 
```

# swap交换两数位置
（是iostream自带的）
```cpp
#include<iostream>  
using namespace std;
int main(){
    int a,b;
    cin>>a>>b;
    swap(a,b);
    cout<<a<<" "<<b;
} 
```

# sort函数
从小到大排序，加了cmp就是从大到小
```cpp
#include<algorithm>
#include<iostream>
using namespace std;
int a[15],n;
bool cmp(int a,int b){
    return a>b;
}
int main(){
    cin>>n;
    for(int i=0;i<n;i++)
        cin>>a[i];
    //sort(a,a+n,cmp);
    sort(a,a+n);
    for(int i=0;i<n;i++)
        cout<<a[i]<<" ";
    return 0;
}
```

# max,min函数
```cpp
#include<iostream>
using namespace std;
int a,b;
int main(){
    cin>>a>>b;
    cout<<max(a,b)<<endl;//最大值
    cout<<min(a,b);//最小值
    return 0;
}
```

# 冒泡排序！！
```cpp
#include<algorithm>
#include<iostream>
using namespace std;
int n,a[100005];
int main(){
    cin>>n;
    for(int i=0;i<n;i++)
        cin>>a[i];
    for(int i=0;i<n;i++)
        for(int j=0;j<n-i-1;j++)
            if(a[j]>a[j+1])
                swap(a[j+1],a[j]);
    for(int i=0;i<n;i++)
        cout<<a[i]<<" ";
    return 0;
}
```

# 结构体
没完全懂，待会儿更新多点。。。主要是还没找到，找完之后还要练。
```cpp
struct Student {    // 学生结构体
    string name;    // 学生姓名
    int grade;      // 学生分数
    Student();  // 无参数构造函数
    Student(string name, int grade) : name(name), grade(grade) {};  // 有参数构造函数
};
``` 

