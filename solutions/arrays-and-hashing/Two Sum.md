# 📝 Two Sum

## 🔗 [Task description on NeetCode](https://neetcode.io/problems/two-integer-sum)

### 💡 Solution

```javascript
class Solution {
	twoSum(nums, target) {
		const hash = {};
		for (let i = 0; i < nums.length; i++) {
			const diff = target - nums[i];
			if (hash[diff] !== undefined) return [hash[diff], i];
			else hash[nums[i]] = i;
		}

		return [];
	}
}
```
