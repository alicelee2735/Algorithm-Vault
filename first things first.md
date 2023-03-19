最大公约数
`int gcd(int a,int b){
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
`
最小公倍数
`long long lcm = a*b/gcd(a,b); `
直接使用gcd函数，要开long long

查找子串
`#include<bits/stdc++.h>
using namespace std;
int main()
{
    string s1 = "123";
    string s2 = "23";
    string s3 = "73";
    cout << s1.find(s2) << endl;;
    unsigned int c = s1.find(s3);
    cout << c << endl;
     
}`

memset初始化数组，所有数设0
`memset(a,0,sizeof(a));`

数组里求最大值，最小值
`
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
`
swap交换两数位置
（是iostream自带的）
`
#include<iostream>  
using namespace std;
int main(){
    int a,b;
    cin>>a>>b;
    swap(a,b);
    cout<<a<<" "<<b;
} `

sort函数
从小到大排序，加了cmp就是从大到小
`#include<algorithm>
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
}`

max,min函数
`#include<iostream>
using namespace std;
int a,b;
int main(){
    cin>>a>>b;
    cout<<max(a,b)<<endl;//最大值
    cout<<min(a,b);//最小值
    return 0;
}`

冒泡排序！！
`#include<algorithm>
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
}`
