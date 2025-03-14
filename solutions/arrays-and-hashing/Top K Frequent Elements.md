# 📝 Top K Frequent Elements

## 🔗 [Task description on NeetCode](https://neetcode.io/problems/top-k-elements-in-list)

### 💡 Solution

```javascript
class Solution {
	topKFrequent(nums, k) {
		const hash = {};
		for (let n of nums) hash[n] = (hash[n] | 0) + 1;
		return Object.entries(hash)
			.sort((a, b) => b[1] - a[1])
			.slice(0, k)
			.map(([key, _]) => +key);
	}
}
```
