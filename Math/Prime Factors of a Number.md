#math 

#### Given a number x, find the prime factors of the number

#### Naive Method
Run a loop from i = 2 to n, if x is divisible by i, i is a prime factor of x.

#### Optimized Method
```cpp
int i = 2;
while(i*i <= x) {
	while(x % i == 0) {
		cout << i << ' ';
		x = x / i;
	}
	i++;
}
if(x > 1) cout << x << ' ';
```

Run a loop from i = 2 to sqrt(x), if x is divisible by the number than i is a prime factor. 
Divide x by i to reduce the further search space.

Why run the loop only till sqrt(x) ?

**Every composite number has at least one prime factor less than or equal to square root of itself.

Proof by contradiction
If there are two prime factors which are greater than sqrt(n), then
`a > sqrt(n) and b > sqrt(n)
`a * *b > sqrt(n) * sqrt(n)
`ab > n
`
which is incorrect, thus proving.

So when we run our loop from 1 to sqrt(n), we exhaust all small composite prime factors till sqrt(n) and thus there can only remain at most 1 prime factor > sqrt(n).


