# 📝 Reorder Linked List

## 🔗 [Task description on NeetCode](https://neetcode.io/problems/reorder-linked-list/question?list=neetcode150)

### 💡 Solution

```javascript
class Solution {
	reorderList(head) {
		if (!head || !head.next) return;

		let mid = this.getMiddle(head);
		let reversedMid = this.reverseList(mid.next);
		mid.next = null;
		this.interleave(head, reversedMid);
	}

	getMiddle(head) {
		let slow = head;
		let fast = head;
		while (fast != null && fast.next !== null) {
			slow = slow.next;
			fast = fast.next.next;
		}
		return slow;
	}

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

	interleave(list1, list2) {
		while (list2 !== null) {
			let tmp1 = list1.next;
			let tmp2 = list2.next;

			list1.next = list2;
			list2.next = tmp1;

			list1 = tmp1;
			list2 = tmp2;
		}
	}
}
```
