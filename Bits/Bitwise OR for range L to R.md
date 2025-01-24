#bit

## Problem Statement 
Given a range of numbers from (L, R) inclusive, find the bitwise OR of all the numbers in the given range.

### Observations
* If we try to bitwise OR all the numbers in our range going from L to R, then it will be unoptimized if the range of numbers is too high.
* Instead if we look at individual bit position, we can say that in order for the that same bit to be set in the answer, there must be at least one number in the range L to R, which has the bit set.

### Approach 1
Let's take a example 
$$ L = 11000010 $$
$$ R = 11001010 $$

Note the common prefix$$ 1100 $$This prefix will always be present in the answer. Rest all bits will be 1. Why ?
Because the first difference of bits 0 & 1 means, there was a position where the 0 flipped to 1.
So it went from 
$$ 011111.... -> 10000... $$
So, rest all positions will become 1 due to the property of Bitwise OR.

### Approach 2
![[Binary Numbers 1 to 15.png]]
At each bit position i, the bit stays either 1 or 0 consecutively for 2<sup>^i</sup> times. 
For **i = 0**, bit flips every 1 positions **010101010**
For **i = 1**, bit flips every 2 positions **001100110011**
For **i = 3**, bit flips every 4 positions **0000111100001111**
Let's say the range of numbers **x** = **R - L + 1**.
If x > 2<sup>^i</sup> , then we know for sure that the i<sup>th</sup> bit is flipped.
If not, then we find which group the bit belongs for L and R.

![[Pasted image 20250110002602.png]]
To find the group numbers for i<sup>th</sup> bit, we divide it by 2^i
$$ x/2^i $$
If the group number is same for L and R and group number is even, then and only then the i<sup>th</sup> bit is unset. In all other cases the bit will be set.