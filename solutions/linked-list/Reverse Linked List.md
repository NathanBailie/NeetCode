# 📝 Reverse Linked List

## 🔗 [Task description on NeetCode](https://neetcode.io/problems/reverse-a-linked-list/question?list=neetcode150)

### 💡 Solution

```javascript
class Solution {
	reverseList(head) {
		let prev = null;
		let current = head;

		while (current !== null) {
			let nextNode = current.next;
			current.next = prev;
			prev = current;
			current = nextNode;
		}

		return prev;
	}
}
```
