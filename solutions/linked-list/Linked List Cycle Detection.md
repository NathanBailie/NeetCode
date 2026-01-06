# 📝 Linked List Cycle Detection

## 🔗 [Task description on NeetCode](https://neetcode.io/problems/linked-list-cycle-detection/question?list=neetcode150)

### 💡 Solution

```javascript
class Solution {
	hasCycle(head) {
		let slow = head;
		let fast = head;

		while (fast !== null && fast.next !== null) {
			slow = slow.next;
			fast = fast.next.next;

			if (slow === fast) return true;
		}

		return false;
	}
}
```
