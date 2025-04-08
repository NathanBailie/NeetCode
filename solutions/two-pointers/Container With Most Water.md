# 📝 Container With Most Water

## 🔗 [Task description on NeetCode](https://neetcode.io/problems/max-water-container)

### 💡 Solution

```javascript
class Solution {
	maxArea(heights) {
		let max = 0;
		let left = 0;
		let right = heights.length - 1;

		while (left < right) {
			const area = Math.min(heights[left], heights[right]) * (right - left);
			max = Math.max(max, area);
			heights[left] < heights[right] ? left++ : right--;
		}

		return max;
	}
}
```
