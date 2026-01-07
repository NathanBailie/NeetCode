# 📝 Copy Linked List with Random Pointer

## 🔗 [Task description on NeetCode](https://neetcode.io/problems/copy-linked-list-with-random-pointer/question?list=neetcode150)

### 💡 Solution

```javascript
// №1
class Solution {
	copyRandomList(head) {
		if (!head) return null;

		let curr = head;

		while (curr) {
			let copy = new Node(curr.val, curr.next, null);
			curr.next = copy;
			curr = copy.next;
		}

		curr = head;
		while (curr) {
			if (curr.random) {
				curr.next.random = curr.random.next;
			}
			curr = curr.next.next;
		}

		curr = head;
		let newHead = head.next;
		let copyCurr = newHead;

		while (curr) {
			curr.next = curr.next.next;
			if (copyCurr.next) {
				copyCurr.next = copyCurr.next.next;
			}

			curr = curr.next;
			copyCurr = copyCurr.next;
		}

		return newHead;
	}
}

// №2
class Solution {
	copyRandomList(head) {
		if (!head) return null;
		const map = new Map();

		let curr = head;
		while (curr) {
			map.set(curr, new Node(curr.val));
			curr = curr.next;
		}

		curr = head;
		while (curr) {
			const copy = map.get(curr);
			copy.next = map.get(curr.next) || null;
			copy.random = map.get(curr.random) || null;

			curr = curr.next;
		}

		return map.get(head);
	}
}
```
