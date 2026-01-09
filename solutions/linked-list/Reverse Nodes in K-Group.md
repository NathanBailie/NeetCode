# 📝 Reverse Nodes in K-Group

## 🔗 [Task description on NeetCode](https://neetcode.io/problems/reverse-nodes-in-k-group/question?list=neetcode150)

### 💡 Solution

```javascript
class Solution {
	reverseKGroup(head, k) {
		let cur = head;
		let group = 0;
		while (cur && group < k) {
			cur = cur.next;
			group++;
		}

		if (group === k) {
			cur = this.reverseKGroup(cur, k);
			while (group-- > 0) {
				let tmp = head.next;
				head.next = cur;
				cur = head;
				head = tmp;
			}
			head = cur;
		}
		return head;
	}
}
```
