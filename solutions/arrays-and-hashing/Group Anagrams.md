# 📝 Group Anagrams

## 🔗 [Task description on NeetCode](https://neetcode.io/problems/anagram-groups)

### 💡 Solution

```javascript
// №1
class Solution {
	groupAnagrams(strs) {
		const map = new Map();

		strs.forEach(str => {
			const count = Array(26).fill(0);
			for (let char of str) count[char.charCodeAt(0) - 97]++;
			const key = count.join('#');
			map.has(key) ? map.get(key).push(str) : map.set(key, [str]);
		});

		return [...map.values()];
	}
}

// №2
class Solution {
	groupAnagrams(strs) {
		const hash = {};

		for (let str of strs) {
			const sortedStr = str.split('').sort().join('');
			(hash[sortedStr] ??= []).push(str);
		}

		return Object.values(hash);
	}
}
```
