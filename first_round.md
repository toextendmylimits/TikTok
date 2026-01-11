First round coding

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

## 49. Group Anagrams
Practice more.  
I group strings by a character frequency signature.  
For each word, I count how many times each letter appears and convert that count into a tuple, which becomes the dictionary key.  
All anagrams share the same frequency tuple, so they end up in the same group.  
This runs in O(n·k) time and avoids sorting.  

# Sliding Window / two pointers

## 11. Container With Most Water
I use two pointers at both ends.  
The area is width times the shorter height.   
At each step, I compute the area, then move the pointer with the smaller height, because the shorter line limits the area.   
Moving the taller one cannot help. This gives an O(n) solution.  

## 76. Minimum Window Substring
I use a sliding window with two pointers. I count required characters from t.   
As I expand the right pointer, I track counts in the window and how many required characters are satisfied.    
Once all are satisfied, I shrink from the left as much as possible while keeping the window valid, updating the best window each time.   
Overall it’s linear because each pointer only moves forward.  

## 424. Longest Repeating Character Replacement  
I use a sliding window and count letters inside it.   
I keep max_freq, the count of the most common letter in the window.  
If window_len - max_freq is more than k, I shrink from the left.  
Otherwise the window is valid, and I update the answer with its length.  

## 239. Sliding Window Maximum
I use a monotonic decreasing deque of indices.  
When adding a new element, I remove smaller elements from the back since they can’t be maximum anymore.  
The front of the deque always holds the max of the current window.  
Each element is added and removed once, so it’s O(n).  

# Stack
## 739. Daily Temperatures
I use a monotonic decreasing stack storing indices.  
As I scan days, if today’s temperature is higher than the stack top, I pop and set the answer as the day difference.  
Then I push today. Each day is processed once, so it’s O(n).  

## 496. Next Greater Element I
I scan nums2 with a decreasing stack.   
When I see a bigger number x, I pop all smaller stack values and record their next greater as x.   
After building this map, I answer each nums1 element by lookup, default -1.  

# Intervals
## 56. Merge Intervals
## 57. Insert Interval

# Practice gain
## 49. Group Anagrams
## 424. Longest Repeating Character Replacement   
## 239. Sliding Window Maximum
## 739. Daily Temperatures
## 496. Next Greater Element I
