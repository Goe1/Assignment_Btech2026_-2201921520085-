"Explanation here..." 
Intuition 🔍
💡 Use a mapping from index to number.
🚀 For each number, maintain a min-heap of indices.
🔄 On update, insert the new index without removing the old one (lazy deletion).
⚡ When querying, pop invalid indices until the top is valid.
⏱️ Efficient operations with O(logn) updates and queries.

Complexity ⚙️
Time complexity:
- change: O(logn),
- find: O(logn) amortized
Space complexity: O(n)