#prefix

### Algorithm

Loop through the array and if the current element is different to previous element than the nearest diff is just the previous index.
Else the nearest will be whatever is the index of previous value as both current and previous values are same.
```cpp
vll arr(n) // input Array

vll nearDiff(n);
nearDiff[0] = -1;
for(int i = 1; i < n; i++) {
	nearDiff[i] = nearDiff[i-1];
	if(arr[i] != arr[i-1]) {
		nearDiff[i] = i-1;
	}
}
```