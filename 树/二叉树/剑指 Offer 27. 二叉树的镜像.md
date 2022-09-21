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
 * @return {TreeNode}
 */
// 递归
// 每一层都翻转
var mirrorTree = function(root) {
    if (root === null) {
        return null;
    }
    let leftTree = mirrorTree(root.left);
    let rightTree = mirrorTree(root.right);
    root.left = rightTree;
    root.right = leftTree;
    return root;
};
```
