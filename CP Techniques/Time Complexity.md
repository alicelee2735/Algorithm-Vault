## What is Time Complexity

Time complexity is a tool for algorithm analysis that helps you calculate roughly how fast your algorithm is. It measures **the number of operations in an algorithm**.
(The USACO grading server can handle around 2*10^8 operations per second.)
Time complexity is denoted with “**Big O notation**” as O(f(n)), aka “asymptotic notation.”

## Calculating Time Complexity
We consider all constant numbers of operations as O(1). For example, input and output and math operations. When there is a loop, the time complexity is the number of times the loop has to iterate multiplied by the number of operations each iteration. Ignore constant factors and lower-order terms. If an algorithm contains multiple blocks of code, the time complexity is considered the worst time out of all loops. 

## Constant Factor
**Completely ignore the constant factor of time complexity**. For example, adding ten numbers together takes longer than adding two. However, there is no difference in time complexity since we ignore the constant factor O(10*1) and O(2*1). Therefore, both complexity counts as O(1). 

## Examples 
### O(1) Complexity
```cpp
int a = 1;
int b = 2;
int c = a + b;
```
```cpp
int n=100;
for(int i = 0; i < n; i++){ //code }
```
### O(n) Complexity
```cpp
int n;
cin>>n;
for(int i = 0; i < n; i++){ //code }
```
```cpp
int n;
cin>>n;
for(int i = 0; i < n+9999; i++){ //code }
```
### O(nm) Complexity
```cpp
int n,m;
cin>>n>>m;
for(int i = 0; i < n; i++){
  for(int j = 0; j < m; j++){
    //code 
  }
}
```
### O(n^2) Complexity
```cpp
int n;
cin>>n;
for(int i = 0; i < n; i++){
  for(int j = 0; j < n; j++){
    //code 
  }
}
```
### O(log n) Complexity
```cpp
int n; 
cin >> n;
for (int i = 1; i < n; i *= 2) { //code }
```
Since log_2 n with base 2 means the number of square root n has to execute to get n<=1, if we iterate from 1 to n with i multiplying itself by 2, it runs for exactly log n times; thus the code represents O(log n) complexity. 
```cpp
int binarySearch(const std::vector<T>& arr, const T& target) {
    int left = 0;
    int right = arr.size() - 1;

    while (left <= right) {
        int mid = left + (right - left) / 2;

        if (arr[mid] == target) {
            return mid;
        } else if (arr[mid] < target) {
            left = mid + 1;
        } else {
            right = mid - 1;
        }
    }

    return -1;
}
```
### O(sqrt(n)) Complexity
```cpp
int n, cnt=0; //count cnt the number of prime factors
cin>>n;
for(int i = 1; i*i <= n; i++){
  if(n%i==0){
    if(i*i==n)
      cnt++;
    else
      cnt+=2;
  }
}
```
Counts the number of prime factors of n. 
