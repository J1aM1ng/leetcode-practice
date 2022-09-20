```js
var CQueue = function() {
    this.stack1 = [], this.stack2 = [];
};
// stack1栈底为队列"头，承接输入；stack2栈顶为队列头，进行输出
/** 
 * @param {number} value
 * @return {void}
 */
CQueue.prototype.appendTail = function(value) {
    this.stack1.push(value);
};

/**
 * @return {number}
 */
CQueue.prototype.deleteHead = function() {
    if (this.stack2.length) {
        return this.stack2.pop();
    } else {
        if (this.stack1.length) {
            while(this.stack1.length) {
                this.stack2.push(this.stack1.pop());
            }
            return this.stack2.pop();
        }
        return -1;
    }
};

/**
 * Your CQueue object will be instantiated and called as such:
 * var obj = new CQueue()
 * obj.appendTail(value)
 * var param_2 = obj.deleteHead()
 */
```

