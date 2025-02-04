"Explanation here..." 
Approach 1: Store nums1 in the HashMap
HashMap stores the frequency of elements from nums1.
In count(), you iterate over nums2 and check if (target - num) exists in the map.
Why it causes TLE:
The elements in nums1 can go up to 10⁹, making the HashMap sparse.
Hash collisions become frequent because of the large key space, making lookups slower.
Even though the number of iterations in count() is fewer (only up to 10⁵), the overhead from large keys slows things down, leading to TLE.
Approach 2: Store nums2 in the HashMap (Better Choice)
HashMap stores the frequency of elements from nums2.
In count(), you iterate over nums1 and check if (target - num) exists in the map.
Why this works better:
The elements in nums2 are smaller (up to 10⁵), making the HashMap compact and faster.
Fewer hash collisions, so lookups are faster.
Even though you iterate over nums1 (which can be large), lookups are fast, so it avoids TLE.