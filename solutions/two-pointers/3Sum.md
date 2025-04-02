# 📝 3Sum

## 🔗 [Task description on NeetCode](https://leetcode.com/problems/3sum/)

### 💡 Solution

```javascript
class Solution {
	threeSum(nums) {
		nums.sort((a, b) => a - b);
		const result = [];

		for (let i = 0; i < nums.length - 2; i++) {
			if (i > 0 && nums[i] === nums[i - 1]) continue;

			let [left, right] = [i + 1, nums.length - 1];
			while (left < right) {
				const sum = nums[i] + nums[left] + nums[right];
				if (sum === 0) {
					result.push([nums[i], nums[left++], nums[right--]]);
					while (nums[left] === nums[left - 1]) left++;
					while (nums[right] === nums[right + 1]) right--;
				} else {
					sum < 0 ? left++ : right--;
				}
			}
		}

		return result;
	}
}
```
