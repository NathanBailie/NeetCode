# 📝 Encode and Decode Strings

## 🔗 [Task description on NeetCode](https://neetcode.io/problems/string-encode-and-decode)

### 💡 Solution

```javascript
class Solution {
	encode(strs) {
		if (!strs.length) return [];
		return strs.reduce((str, word) => (str += `(${word.length}#)${word}`), '');
	}

	decode(str) {
		if (!str.length) return [];
		return str.split(/\(\d+#\)/).slice(1);
	}
}
```
