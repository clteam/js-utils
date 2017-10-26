# js 常用一些 function

## Add

### :sparkle: 获取字符串的长度，区分中文和英文
```js
/**
 * 获取字符串的长度，区分中文和英文
 * @param str
 * @returns {number}
 */
exports.strLength = function (str) {
  let len = 0
  for (let i = 0; i < str.length; i++) {
    let c = str.charCodeAt(i)
    // 单字节加1
    if ((c >= 0x0001 && c <= 0x007e) || (c >= 0xff60 && c <= 0xff9f)) {
      len++
    } else {
      len += 2
    }
  }
  return len
}
```
举个栗子：
```js
console.log(strLength('Dunizb')) // 6
console.log(strLength('小仙女')) // 6
```
