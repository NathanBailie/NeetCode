# 📝 Contains Duplicate

## 🔗 [Task description on NeetCode](https://neetcode.io/problems/duplicate-integer)

### 💡 Solution

```javascript
class Solution {
	hasDuplicate(nums) {
		return nums.length !== new Set(nums).size;
	}
}
```
