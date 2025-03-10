# 📝 Valid Anagram

## 🔗 [Task description on NeetCode](https://neetcode.io/problems/is-anagram)

### 💡 Solution

```javascript
// #1
class Solution {
	isAnagram(str1, str2) {
		if (str1.length !== str2.length) return false;
		const hash = {};

		for (let l of str1) hash[l] = (hash[l] || 0) + 1;

		for (let l of str2) {
			if (hash[l] > 0) hash[l] -= 1;
			else return false;
		}

		return true;
	}
}

// №2
// class Solution {
// 	sortString(str) {
// 		return [...str].sort().join('');
// 	}
// 	isAnagram(s, t) {
// 		return this.sortString(s) === this.sortString(t)
// 	}
// }
```
