# Introduction to Data Structures

## What are Data Structures?
Data structures allow you to store and organize different types of data(eg, int, string, etc.) and use these information efficiently. 
In C++, the STL(Standard Template Library) data structures can store any type of data. Its data type is declared by what you insert inside ```<>```. For example:
```vector<int> array; ```.
Every STL data structure allows you to use the size() and empty() methods, explained later.
This note covers arrays, dynamic arrays, iterating, stacks, queues, sets, maps, and pairs. 

## Arrays 
An array is a special kind of data type that allows users to store multiple values of the same data type inside.
There exists a class ```array``` in STL, simply declared like this:
```cpp
array<int, 20> a;
```

## Dynamic Arrays
A dynamic array is a special kind of array that is "dynamic." This means the size of the dynamic array can be modified
There are different ways of declaring a dynamic array(vector, the most commonly used one) shown below. 
```cpp
vector<int> v(n); //creates a vector "v" with the size of n, all values initialized to 0
```
```cpp
vector<int> v; //another way, same as above
v.resize(n);
```
```cpp
vector<int> v = {1,2,3} //creates a vector with three elements 1,2,3 with size of 3
```
```cpp
vector<int> v(5,1) //creates a vector size of 5, with all elements value initialized 1
```

## Iterators
Iterators are pointers that point towards an element in a data structure. 
### Vector iterators
Vector iterators are often used to define the range of a data structure. The two useful iterators are ```v.begin()``` that points towards the first element, and ```v.end()``` pointing towards a position **after** the last element. For example:
```cpp
vector<int> v = {4,3,2,1};
sort(v.begin(),v.end());
for(int i=v.begin();i!=v.end();++i) cout<<*i<<" ";
//or for(auto i : v) cout<<i<<" ";
//or for(vector<int>::iterator i = v.begin();i!=v.end();++i) cout<<*i<<" ";
//output: 1 2 3 4
```
### Set iterators
Iterators of a set are often used to access elements in a set.
Set: A container that stores a **sorted** list of **unique** numbers. For example:
```cpp
set<int> s={1,2,5,5,2};
for(auto i = s.begin();i!=s.end();++i) cout<<*i<<" ";
//output: 1 2 5
//or: for(auto i : s) cout<<i<<" ";
//same output
```

## Common actions(vector)
```cpp
vector<int> v(5);
v.push_back(2); //v={0,0,0,0,0,2} appends 2 to the end of the vector
```
```cpp
vector<int> v;
v.push_back(1); 
v.push_back(2);
v.push_back(3); //v={1,2,3} the vector automatically resizes itself
v.erase(v.end()-1) //v={1,2}
v[0] = 3; //v={3,2}
```
