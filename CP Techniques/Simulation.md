# Simulation

## What is Simulation?
Simulation is directly simulating what the problem statement tells you to do. Since there are no algorithms required, the program is written in a direct and straightforward manner. \
**Key Characteristics**:
- Follows problem description literally
- Uses conditional statements and loops heavily
- Often involves tracking state changes over time

## Example Problem 1
[USACO Jan 2019 Bronze 1. Shell Game](https://usaco.org/index.php?page=viewproblem2&cpid=891)

### Overview
**Rules**:
1. Three shells named 1,2,3 (positions 1, 2, 3)
2. Pebble starts under one shell
3. N swaps performed
4. ```a``` and ```b``` are swapped, ```g``` is the guess

### Solution Code(C++)
```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    //freopen("shell.in","r",stdin);
    //freopen("shell.out","w",stdout);
    int N;
    cin>>N;
    vector<int> guess(3);
    vector<int> shells = {0,1,2,3}; 
    while(N--){
        int a,b,g;
        cin>>a>>b>>g;
        swap(shells[a],shells[b]);
        guess[shells[g]]++;
    }
   cout<<max({guess[1],guess[2],guess[3]}); 
}
```

## Example Problem 2
[USACO Dec 2018 Bronze 1. Mixing Milk](https://usaco.org/index.php?page=viewproblem2&cpid=855)

### Overview
**Pour milk(100 times)**:
- 1->2->3->1 sequence
- Therefore, for the i_th pour, bucket[i%3] pours into bucket[(i+1)%3]

### Solution Code(C++)
```cpp
#include <bits/stdc++.h>
using namespace std;
#define ll long long
int main() {
    //freopen("mixmilk.in","r",stdin);
    //freopen("mixmilk.out","w",stdout);
    vector<ll> cap(4),amount(4);
    for(int i=0;i<=2;++i) cin>>cap[i]>>amount[i];

    const int N = 100;
    for(int i=0;i<N;++i){
        ll bucket1 = i%3; //index of the first bucket
        ll bucket2 = (i+1)%3; //index of where the first bucket pours into
        ll pourMilk = min((cap[bucket2]-amount[bucket2]),amount[bucket1]);
        amount[bucket2] += pourMilk;
        amount[bucket1]-= pourMilk;
    }
    for(int i=0;i<=2;++i) cout<<amount[i]<<"\n";
}
```
