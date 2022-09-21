```js
/**
 * Definition for a binary tree node.
 * function TreeNode(val) {
 *     this.val = val;
 *     this.left = this.right = null;
 * }
 */
/**
 * @param {TreeNode} root
 * @return {boolean}
 */
// 递归实现DFS
// 注意镜像的比较是对比哪些，怎么传递归值
var isSymmetric = function(root) {
    if (root === null) {
        return true;
    }
    return dfs(root.left, root.right);
};
const dfs = (left, right) => {
    if (left === null && right === null) {
        return true;
    }
    if (left === null || right === null || left.val !== right.val) {
        return false;
    }
    // left !== null && right !== null
    return dfs(left.left, right.right) && dfs(right.left, left.right);
}
```
