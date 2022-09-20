```js
/**
 * @param {number[]} nums
 * @return {number}
 */
// 哈希表
var findRepeatNumber = function(nums) {
    const st = new Set();
    const len = nums.length;
    for (let i = 0; i < len; i++) {
        if (st.has(nums[i])) {
            return nums[i];
        } else {
            st.add(nums[i]);
        }
    }
};
```

