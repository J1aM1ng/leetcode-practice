```js
/**
 * Definition for singly-linked list.
 * function ListNode(val) {
 *     this.val = val;
 *     this.next = null;
 * }
 */
/**
 * @param {ListNode} l1
 * @param {ListNode} l2
 * @return {ListNode}
 */
// 遍历, 归并
const mergeTwoLists = function(list1, list2) {
    const ans = new ListNode(-1);
    let prev = ans;
    while (list1 !== null && list2 !== null) {
        if (list1.val <= list2.val) {
            prev.next = new ListNode(list1.val);
            list1 = list1.next;
        } else {
            prev.next = new ListNode(list2.val);
            list2 = list2.next;
        }
        prev = prev.next;
    }
    prev.next = list1 === null ? list2 : list1;
    return ans.next;
};
```

