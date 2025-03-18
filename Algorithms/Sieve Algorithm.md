# Sieve of Eratosthenes


## What is Sieve of Eratosthenes
Sieve of Eratosthenes is an ancient algorithm that finds all prime numbers in a given range. It is also used to find all divisors of a number with a faster time complexity.

## Sieve Algorithm
1. The algorithm starts by generating a boolean array ```Boolarray``` to store whether ```i``` is a prime number or not.
2. Every number in the array is set to be TRUE by default.
3. The outer loop of the algorithm iterates Boolarray from 2 to ```sqrt(n)```.
- Inner loop iterates through j and accumulates by i(for all multiples of i), all multiples are marked FALSE(since these are not prime numbers).
- Inner loop works by marking FALSE on all multiples of ```i```
4. We are left with ```b``` with all prime numbers being TRUE in the range of 1 to n.

## Time Complexity
The time complexity of the above logic is O(n log log n).

## Example in C++
```cpp
#include<iostream>
using namespace std;

int main(){
    int n;
    cin>>n;
    bool Boolarray[n+1];
    for(int i = 2; i <= n; i++) {
      Boolarray[i]=true;
    }
    for (int i = 2; i * i <= n; i++) {
        if (Boolarray[j] == true) {
            for (int j = 2 * i; j <= n; j += i) {
            Boolarray[k] = false;
            }
        }
    }
    for(int i = 2; i <= n; i++) {
        if(Boolarray[i]==true)
            cout<<i<<" ";
    }
    return 0;
}
```
