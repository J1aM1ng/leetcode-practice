```js
/**
 * Definition for singly-linked list.
 * function ListNode(val) {
 *     this.val = val;
 *     this.next = null;
 * }
 */
/**
 * @param {ListNode} head
 * @return {number[]}
 */
// 栈（辅助栈）O(n)时间
var reversePrint = function(head) {
    const ans = [];
    const stack = [];
    while (head) {
        stack.push(head.val);
        head = head.next;
    }
    while (stack.length) {
        ans.push(stack.pop());
    }
    return ans;
};
```

