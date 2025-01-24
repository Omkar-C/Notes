### Check if a number is a power of two
```cpp
n & !(n & (n-1))
```

This is because if a number if power of 2, there will only be one bit set.
For eg :- 1000 = 8 or 10 = 2
Hence, n-1 will be previous number which has all the bits set except the most significant bit which is power of 2.
Thus, bitwise and operation of these two numbers will return 0.

### The least significant bit number is a divisor of the number
Ex :- 10000100
Then 100 is a divisor
