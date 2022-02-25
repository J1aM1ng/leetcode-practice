```js
/**
 * @param {number} a
 * @param {number} b
 * @return {number}
 */
// 异或模拟求无进位和，与运算求每位的进位数
const add = (a, b) => {
    // 进位数为0时退出
    // 从低位到高位一位位地求
    while (b !== 0) {
        // 进位数
        let c = (a & b) << 1;
        // a <= 无进位和
        a ^= b;
        // b <= 进位数
        b = c;
    }
    // 退出时说明无进位，返回a即可
    return a;
};
```

