## p20 11
```
#pragma GCC optimize(3, "Ofast", "inline")
#include <bits/stdc++.h>
#define start ios::sync_with_stdio(false);cin.tie(0);cout.tie(0);
#define rep(z, x, y) for(int z=x;z<=y;++z)
typedef long long ll;
const int maxn = (ll) 2e5 + 5;
using namespace std;
int a[maxn],b[maxn];
int n,m;
void midd(int mid){
	int p1=1,p2=1,cnt=0,last=0;
	while(++cnt <= mid){
		if(a[p1]<b[p2] && p1<=n){
			last=p1;p1++;
		}else if(a[p1]>=b[p2] && p2<=m){
			last=p2;p2++;
		}
	}
	if(last == p1) cout<<a[p1];
	else cout<<b[p2];
}
int main() { 
	start;
	cin>>n>>m;
	rep(i,1,n) cin>>a[i];
	rep(i,1,m) cin>>b[i];
	int mid = ceil((n+m)*0.5);
	midd(mid);
	return 0; 
}
```
## p21 13
```
#pragma GCC optimize(3, "Ofast", "inline")
#include <bits/stdc++.h>
#define start ios::sync_with_stdio(false);cin.tie(0);cout.tie(0);
#define rep(z, x, y) for(int z=x;z<=y;++z)
#define repd(z, x, y) for(int z=x;z>=y;--z)
typedef long long ll;
const int maxn = (ll) 2e5 + 5;
const int mod = 998244353;
const int inf = 0x3f3f3f3f;
using namespace std;
int n;
int a[maxn];
bool b[maxn];
int main() { 
	start;
	cin>>n;
	rep(i,1,n){
		cin>>a[i];
		if(a[i] && a[i] <= n) b[a[i]] = 1;
	}
	int ans = 0;
	rep(i,1,n){
		if(!b[i]){
			ans = i;break;
		}
	}
	if(!ans) ans = n+1;
	cout<<ans;
	return 0; 
}
```
