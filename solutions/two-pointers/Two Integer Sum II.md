# 📝 Two Integer Sum II

## 🔗 [Task description on NeetCode](https://neetcode.io/problems/two-integer-sum-ii)

### 💡 Solution

```javascript
class Solution {
	twoSum(nums, target) {
		let left = 0;
		let right = nums.length - 1;

		while (left < right) {
			let sum = nums[left] + nums[right];

			if (sum === target) return [left + 1, right + 1];
			sum < target ? left++ : right--;
		}
		return [];
	}
}
```
