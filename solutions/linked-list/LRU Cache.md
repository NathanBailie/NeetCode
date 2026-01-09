# 📝 LRU Cache

## 🔗 [Task description on NeetCode](https://neetcode.io/problems/lru-cache/question?list=neetcode150)

### 💡 Solution

```javascript
class Node {
	constructor(key, value) {
		this.key = key;
		this.value = value;
		this.prev = null;
		this.next = null;
	}
}

class LRUCache {
	constructor(capacity) {
		this.capacity = capacity;
		this.cache = new Map();

		this.head = new Node(0, 0);
		this.tail = new Node(0, 0);
		this.head.next = this.tail;
		this.tail.prev = this.head;
	}

	_remove(node) {
		let prev = node.prev;
		let next = node.next;
		prev.next = next;
		next.prev = prev;
	}

	_add(node) {
		node.next = this.head.next;
		node.prev = this.head;
		this.head.next.prev = node;
		this.head.next = node;
	}

	get(key) {
		if (this.cache.has(key)) {
			const node = this.cache.get(key);
			this._remove(node);
			this._add(node);
			return node.value;
		}
		return -1;
	}

	put(key, value) {
		if (this.cache.has(key)) {
			this._remove(this.cache.get(key));
		}

		const newNode = new Node(key, value);
		this.cache.set(key, newNode);
		this._add(newNode);

		if (this.cache.size > this.capacity) {
			const lru = this.tail.prev;
			this._remove(lru);
			this.cache.delete(lru.key);
		}
	}
}
```
