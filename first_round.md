# First round coding

## 560. Subarray Sum Equals K
I scan the array and keep a running prefix sum.   
If the current sum is S, any earlier prefix sum S - k means the subarray between them sums to k.   
I store counts of prefix sums in a hash map and add freq[S-k] to the answer each step.   
Initialize freq[0]=1 to count subarrays starting at index 0.”  
