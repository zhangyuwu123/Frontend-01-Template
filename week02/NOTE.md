## 作业
UTF8 Encoding函数
```
function encodeUTF(text) {
    const code = encodeURIComponent(text);
    const bytes = [];
    for (let i = 0; i < code.length; i++) {
        const c = code.charAt(i);
        if (c === '%') {
            const hex = code.charAt(i + 1) + code.charAt(i + 2);
            const hexVal = parseInt(hex, 16);
            bytes.push(hexVal);
            i += 2;
        } else bytes.push(c.charCodeAt(0));
    }
    return bytes;
}
```
匹配String直接量
```
var regxStr = /^(?=.*[a-zA-Z])(?=.*\d)(?=.*[\u0021-\u002F\u003A-\u0040\u005B-\u0060\u007B-\u007E])[\u0021-\u007E]{6,16}$/g
```
ASCII
```
var regAsc = /^(?=.*[a-zA-Z])(?=.*\d)(?=.*[\x21-\x2F\x3A-\x40\x5B-\x60\x7B-\x7E])[\x21-\x7E]{6,16}$/g
```
单双引号
```
var regSgl = /(?:[^"\\]|\\.)*"|'(?:[^'\\]|\\.)*/
```
正则匹配Number直接量
```
var regNum = /(^-?\\d+$)|(^(-?\\d+)(\\.\\d+)?$)|(^[01]+$)|(^[0-7]+$)|((^0x[a-f0-9]{1,2}$)|(^0X[A-F0-9]{1,2}$)|(^[A-F0-9]{1,2}$)|(^[a-f0-9]{1,2}$))/g
```

## 心得体会
本周先从语言层面学习了语言的产生式（BNF），之前也看过AST的相关技术，当时理解起来非常费劲，学习了BNF在回头去看AST感觉熟悉多了，给我的其实是，技术的东西要抓住本质，功能层面的只是为了解决问题，而问题又是解决不完的；以后再学习一个上层应用内的技术时，应该先学习好基础，找到本质；这周再工作中处理不通过flash播放flv视频流时，找到了flv，用老师的追溯法，找到了flv的底层实现细节Media Source Extensions、demux，了解这些可以说自己可以实现一个简易的flv播放器了。
