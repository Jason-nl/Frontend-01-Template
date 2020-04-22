1. 数字正则
```javascript
/^((0b(0|(1[01]*)))|(0o(0|([1-7][0-7]*)))|(0x(0|([1-9a-fA-F][0-9a-fA-F]*)))|(0|([1-9][0-9]*))\.?([0-9]*(([eE][\+-]?)?(0|([1-9][0-9]*)))?))$/
```
2. utf-8编码函数
```javascript
function encodeUtf8(text) {
    const code = encodeURIComponent(text);
    const bytes = [];
    for (var i = 0; i < code.length; i++) {
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
3. 写一个正则表达式，匹配所有的字符串直接量，单引号和双引号

```javascript
/^(("([^"]|\")*")|('([^']|\')*'))$/
```