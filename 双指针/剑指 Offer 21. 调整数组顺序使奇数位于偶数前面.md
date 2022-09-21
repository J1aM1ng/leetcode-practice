```js
/**
 * @param {number[]} nums
 * @return {number[]}
 */
// 首尾双指针，首指针从前向后扫，尾指针从后向前扫
// 从首部找偶数，从尾部找奇数，交换，直到首尾指针重合
var exchange = function(nums) {
    const len = nums.length;
    const ans = nums;
    let left = 0, right = len - 1;
    while (left < right) {
        if (nums[left] % 2 !== 0) {
            ++left;
            continue;
        }
        if (nums[right] % 2 !== 1) {
            --right;
            continue;
        }
        let tmp = nums[left];
        nums[left] = nums[right];
        nums[right] = tmp;
        --right, ++left;
    }
    return ans;
};
```

