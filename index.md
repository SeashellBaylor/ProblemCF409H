## 题解 CF409H 【A + B Strikes Back】

~~本蒟蒻又来刷水题辣~~

代码如下：

朴素做法：
```cpp
#include<bits/stdc++.h>
using namespace std;
int main()
{
    int a,b;
    cin>>a>>b;
    cout<<a+b;
    return 0;
}
```

有了快读：
```cpp
#include<bits/stdc++.h>
using namespace std;
int a,b;
int read()
{
	int r=0,f=1;
	char c=getchar();
	while((c<'0'||c>'9')&&c!='-')
		c=getchar();
	if(c=='-')
		f=-1,c=getchar();
	while(c<='9'&&c>='0')
		r=r*10+c-'0',c=getchar();
	return r*f;
}
int main()
{
	a=read();
    	b=read();
        printf("%d",a+b);
        return 0;
}
```
用高精度：

```cpp
#include <bits/stdc++.h>
#define ri register int
#define maxn 510
using namespace std;
string s1,s2;
int a[maxn],b[maxn],c[maxn],la,lb,len;
int main()
{
    getline(cin,s1);
    getline(cin,s2);
    if(s1[0]==48&&s2[0]==48){
        printf("0");
        return 0;
    }
    la=s1.size();
	lb=s2.size();
    for(ri i=0;i<la;i++)
        a[la-i-1]=s1[i]-48;
    for(ri i=0;i<lb;i++)
        b[lb-i-1]=s2[i]-48;
    len=max(la,lb);
    for(ri i=0; i<len; i++)
	{
        c[i]+=a[i]+b[i];
        c[i+1]=c[i]/10;
        c[i]%=10;
    }
    len++;
    while(c[len]==0)
        len--; 
    for(ri i=len; i>=0; i--)
        printf("%d",c[i]);
    return 0;
}
```
