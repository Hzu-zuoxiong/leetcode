# 最长公共前缀

编写一个函数来查找字符串数组中的最长公共前缀。

如果不存在公共前缀，返回空字符串 `""`。

**示例 1:**

```
输入: 
["flower","flow","flight"]
输出:
 "fl"
```

**示例 2:**

```
输入: 
["dog","racecar","car"]
输出:
 ""
解释:
 输入不存在公共前缀。
```

**说明:**

所有输入只包含小写字母 `a-z` 。

---

## AC代码：

```js
/**
 * @param {string[]} strs
 * @return {string}
 */
var longestCommonPrefix = function(strs) {
    let prefix = strs[0] || '';
    let l = strs.length;
    for(let i = 1; i < l; i++) {
        let str = strs[i];
        let len = prefix.length;
        for(let j = 0; j < len; j++) {
            if(str[j] !== prefix[j]) {
                prefix = str.slice(0, j);
                break;
            }
        }
    }
    return prefix;
};
```



