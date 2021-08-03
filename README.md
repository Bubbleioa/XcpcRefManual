# 简介

> An awesome project.
> 
$$
f(x) = \int_{-\infty}^\infty
    \hat f(\xi)\,e^{2 \pi i \xi x}
    \,d\xi
$$
```cpp
#include<bits/stdc++.h>
using namespace std;
#define ll long long
const int maxn=2e5+10;
ll a[maxn];
int main()
{
    a[0]=1;
    for(int i=1;i<=30;i++)
    {
        a[i]=a[i-1]*3;
        //cout<<a[i]<<endl;
    }
    int _;cin>>_;
    while(_--)
    {
        ll n,x;cin>>n;
        for(int i=1;i<=n;i++)cin>>x;
        ll k=lower_bound(a,a+30,n)-a;
        if(n==pow(3,k))k++;
        ll ans=0;
        for(int i=0;i<k;i++)ans+=a[i];
        ans+=2*(n%3);
        cout<<ans<<endl;
    }
}

```