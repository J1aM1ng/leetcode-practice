```js
/**
 * @param {string} s
 * @return {character}
 */
// 用哈希表存频数
// O(n)
const firstUniqChar = (s) => {
    const mp = new Map();
    for (let i = 0; i < s.length; i++) {
        if(!mp.has(s[i])) {
            mp.set(s[i], 1);
        } else {
            mp.set(s[i], mp.get(s[i]) + 1);
        }
    }
    for (const [char, frequency] of mp) {
        if (frequency === 1) {
            return char;
        }
    }
    return ' ';
};
```

