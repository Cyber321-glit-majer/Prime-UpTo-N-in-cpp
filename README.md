# Prime-UpTo-N-in-cpp

**

Given a number, let’s say 10. Can you tell all the divisors of the number?

For 10, there are 4 divisors (1, 2, 5 & 10).
Let’s take 5, it has 2 divisors (1 & 5).

A Prime number is a number that has exactly two divisors → 1 and itself.
Note: 1 is not a prime number.

Divisors of Numbers:
2 → 1, 2
3 → 1, 3
5 → 1, 5
7 → 1, 7

Given a number, find all the prime numbers from 1 to that number.

Example
primesUptoN(20) → 2, 3, 5, 7, 11, 13, 17, 19

Testing
Input format
First-line contains ‘T’ denoting the number of independent test cases.

For each test case, a line containing an integer ‘n’.

Output format
For each test case, print a space separated list of all the prime numbers between 1 and ‘n’ in ascending order.

Examples
Sample Input
3
5
1
12
Expected Output
2 3 5

2 3 5 7 11
Constraints
1 <= T <= 100

1 <= n <= 10000

**


**CODE**

```



#include <bits/stdc++.h>

using namespace std;

bool isPrime(int n)
{
    // Corner case
    if (n <= 1)
        return false;
 
    // Check from 2 to n-1
    for (int i = 2; i < n; i++)
        if (n % i == 0)
            return false;
 
    return true;
}
vector<int> primesUptoN(int n) {
    int cnt=0;
	vector<int>v;
	 for(int i=2;i<=n;i++)
	 {
		 if(isPrime(i))
		 {
			 v.push_back(i);
		 }
	 }
	return v;
}
int main()
{
  int n;
  cin>>n;
  
  vector<int>v1;
  v1=primesUptoN(n);
   for(int i=0;i<v1.size();i++)
   {
       cout<<v1[i]<<" ";
   }
   cout<<endl;

    return 0;
}
