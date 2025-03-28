# 📝 Products of Array Except Self

## 🔗 [Task description on NeetCode](https://neetcode.io/problems/products-of-array-discluding-self)

### 💡 Solution

```javascript
// №1
class Solution {
	productExceptSelf(nums) {
		const result = new Array(nums.length).fill(1);

		for (let i = 0, left = 1, right = 1; i < nums.length; i++) {
			result[i] *= left;
			left *= nums[i];

			result[nums.length - 1 - i] *= right;
			right *= nums[nums.length - 1 - i];
		}

		return result;
	}
}

// №2
class Solution {
	productExceptSelf(nums) {
		let result = [];
		const multiplicate = arr => arr.reduce((acc, n) => acc * n, 1);

		nums.forEach((_, i) => {
			let left = multiplicate(nums.slice(0, i));
			let right = multiplicate(nums.slice(i + 1));
			result.push(left * right);
		});

		return result;
	}
}
```
