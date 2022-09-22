```js
/**
 * Definition for a binary tree node.
 * function TreeNode(val) {
 *     this.val = val;
 *     this.left = this.right = null;
 * }
 */
/**
 * @param {TreeNode} A
 * @param {TreeNode} B
 * @return {boolean}
 */
// 先序遍历 递归
// 先序遍历树A中的每个节点
var isSubStructure = function(A, B) {
    // 使用递归判断以A为根节点的子树是否包含树B
    const recursion = (A, B) => {
        if (B === null) {
            return true;
        } else if (A === null || A.val !== B.val) {
            return false;
        } else {
            return recursion(A.left, B.left) && recursion(A.right, B.right);
        }
    }
    if (A === null || B === null) {
        return false;
    }
    // 根左右
    return recursion(A, B) || isSubStructure(A.left, B) || isSubStructure(A.right, B);
};
```
