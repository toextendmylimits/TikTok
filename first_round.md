# First round coding

## 560. Subarray Sum Equals K
I scan the array and keep a running prefix sum.   
If the current sum is S, any earlier prefix sum S - k means the subarray between them sums to k.   
I store counts of prefix sums in a hash map and add freq[S-k] to the answer each step.   
Initialize freq[0]=1 to count subarrays starting at index 0.”  

## 347. Top K Frequent Elements
I count frequencies, then use a min-heap of size k.  
Each time I add an element, if the heap exceeds k, I remove the smallest frequency.  
In the end, the heap contains the k most frequent elements.  

## 3. Longest Substring Without Repeating Characters
I use a sliding window with two pointers.  
I track the last index of each character in a hash map.  
When I see a repeated character, I move the left pointer to one position after its previous index, using max to avoid moving backward.  
At each step, I update the window length.  
This runs in O(n) time.  
