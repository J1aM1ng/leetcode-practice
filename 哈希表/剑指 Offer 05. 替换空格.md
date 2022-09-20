```js
/**
 * @param {string} s
 * @return {string}
 */
// 遍历 O(n)时间
var replaceSpace = function(s) {
    const len = s.length;
    let ans = '';
    for (let i = 0; i < len; i++) {
        if (s[i] === ' ') {
            ans += '%20';
        } else {
            ans += s[i];
        }
    }
    return ans;
};
```

