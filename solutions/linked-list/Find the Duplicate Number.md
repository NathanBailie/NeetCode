# 📝 Find the Duplicate Number

## 🔗 [Task description on NeetCode](https://neetcode.io/problems/find-duplicate-integer/question?list=neetcode150)

### 💡 Solution

```javascript
class Solution {
	findDuplicate(nums) {
		let slow = nums[0];
		let fast = nums[0];

		do {
			slow = nums[slow];
			fast = nums[nums[fast]];
		} while (slow !== fast);

		slow = nums[0];

		while (slow !== fast) {
			slow = nums[slow];
			fast = nums[fast];
		}

		return slow;
	}
}
```
