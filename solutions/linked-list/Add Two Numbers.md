# 📝 Add Two Numbers

## 🔗 [Task description on NeetCode](https://neetcode.io/problems/add-two-numbers/question?list=neetcode150)

### 💡 Solution

```javascript
class Solution {
	addTwoNumbers(l1, l2) {
		let dummy = new ListNode(-1);
		let curr = dummy;
		let carry = 0;

		while (l1 !== null || l2 !== null || carry > 0) {
			let val1 = l1 !== null ? l1.val : 0;
			let val2 = l2 !== null ? l2.val : 0;

			let sum = val1 + val2 + carry;

			carry = Math.floor(sum / 10);
			let newNodeValue = sum % 10;

			curr.next = new ListNode(newNodeValue);
			curr = curr.next;

			if (l1 !== null) l1 = l1.next;
			if (l2 !== null) l2 = l2.next;
		}

		return dummy.next;
	}
}
```
