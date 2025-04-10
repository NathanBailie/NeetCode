# 📝 Trapping Rain Water

## 🔗 [Task description on NeetCode](https://neetcode.io/problems/trapping-rain-water)

### 💡 Solution

```javascript
class Solution {
	trap(height) {
		let left = 0,
			right = height.length - 1;
		let leftMax = 0,
			rightMax = 0;
		let result = 0;

		while (left <= right) {
			if (height[left] < height[right]) {
				leftMax = Math.max(leftMax, height[left]);
				result += leftMax - height[left++];
			} else {
				rightMax = [Math.max(rightMax, height[right])];
				result += rightMax - height[right--];
			}
		}

		return result;
	}
}
```
