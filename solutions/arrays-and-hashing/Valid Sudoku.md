# 📝 Valid Sudoku

## 🔗 [Task description on NeetCode](https://neetcode.io/problems/valid-sudoku)

### 💡 Solution

```javascript
class Solution {
	isValidSudoku(board) {
		// Row check
		for (let i = 0; i < 9; i++) {
			const rowSet = new Set();
			for (let j = 0; j < 9; j++) {
				if (board[i][j] !== '.') {
					if (rowSet.has(board[i][j])) {
						return false;
					}
					rowSet.add(board[i][j]);
				}
			}
		}

		// Column check
		for (let j = 0; j < 9; j++) {
			const colSet = new Set();
			for (let i = 0; i < 9; i++) {
				if (board[i][j] !== '.') {
					if (colSet.has(board[i][j])) {
						return false;
					}
					colSet.add(board[i][j]);
				}
			}
		}

		// Subgrid (3x3) check
		for (let k = 0; k < 9; k++) {
			const subgridSet = new Set();
			for (let i = Math.floor(k / 3) * 3; i < Math.floor(k / 3) * 3 + 3; i++) {
				for (let j = (k % 3) * 3; j < (k % 3) * 3 + 3; j++) {
					if (board[i][j] !== '.') {
						if (subgridSet.has(board[i][j])) {
							return false;
						}
						subgridSet.add(board[i][j]);
					}
				}
			}
		}

		return true;
	}
}
```
