```
#include<bits/stdc++.h>
using namespace std;
const int maxn = 1e6 + 7;
int n,m;
vector<int> a(maxn);
vector<vector<int>> ss;
/*void quick_sort(vector<int> arr&, const int len) {
  if (len <= 1) return;
  // 随机选择基准（pivot）
  const int pivot = arr[rand() % len];
  // i：当前操作的元素
  // j：第一个等于pivot的元素
  // k：第一个大于pivot的元素
  int i = 0, j = 0, k = len;
  // 完成一趟三路快排，将序列分为：小于pivot的元素 ｜ 等于pivot的元素 ｜
  // 大于pivot的元素
  while (i < k) {
    if (arr[i] < pivot)
      swap(arr[i++], arr[j++]);
    else if (pivot < arr[i])
      swap(arr[i], arr[--k]);
    else
      i++;
  }
  // 递归完成对于两个子序列的快速排序
  quick_sort(arr, j);
  quick_sort(arr + k, len - k);
}*/
/*if (l >= r) return;
    int i = l - 1, j = r + 1, x = q[l + r >> 1];
    while (i < j)
    {
        do i ++ ; while (q[i] < x);
        do j -- ; while (q[j] > x);
        if (i < j) swap(q[i], q[j]);
    }
    quick_sort(q, l, j);
    quick_sort(q, j + 1, r);
*/
void q_split(int a,int b){
    int l = 0,r = ss[a].size()-1;
    int i = l - 1, j = r + 1, x = ss[a][l + r >> 1];
    while (i < j){
        do i ++ ; while (ss[a][i] < x);
        do j -- ; while (ss[a][j] > x);
        if (i < j) swap(ss[a][i], ss[a][j]);
    }
    int mid1 = j;
    l = 0,r = ss[b].size()-1;
    i = l - 1, j = r + 1, x = ss[b][l + r >> 1];
    while (i < j){
        do i ++ ; while (ss[b][i] < x);
        do j -- ; while (ss[b][j] > x);
        if (i < j) swap(ss[b][i], ss[b][j]);
    }
    int mid2 = j;
    vector<int> temp;
    temp.assign(ss[a].begin(),ss[a].begin()+
}
void split(int l,int r){
    if(l>=r) return ;
    int mid = l+r >> 1;
    q_split(l,l+mid);
    split(l,mid);
    split(mid+1,r);
}
void solve(){
    int sl = ss.size();
    split(1,sl);
}
void output(){
    for(int i=1;i<=n;i++) cout<<a[i]<<' ';
    cout<<endl;
}
int main(){
    cin>>n;
    for(int i=1;i<=n;i++) cin>>a[i];
    for(int i=1;i<n;i++) if(a[i] > a[i+1]) swap(a[i],a[i+1]);
    output();
    cin>>m;
    const int bnd = pow(2,m);
    ss.push_back(vector<int> ());
    for(int i=0;i<bnd;i++){
        vector<int> temp;
        temp.assign(a.begin()+1+i*n/bnd,a.begin()+1+(i+1)*n/bnd);
        ss.push_back(temp);
    }
    //solve();
    output();
}
```
