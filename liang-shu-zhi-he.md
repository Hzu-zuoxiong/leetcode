# 两数之和

给定一个整数数组和一个目标值，找出数组中和为目标值的**两个**数。

你可以假设每个输入只对应一种答案，且同样的元素不能被重复利用。

**示例:**

```
给定 nums = [2, 7, 11, 15], target = 9

因为 nums[0] + nums[1] = 2 + 7 = 9
所以返回 [0, 1]
```

## **AC代码：**

```js
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number[]}
 */
var twoSum = function(nums, target) {
    let len = nums.length;
    let hash = [];
    for(let i = 0; i < len; ++i) {
        let n = nums[i];
        if(hash[n] >= 0) {
            return [hash[n], i];
        }
        hash[target - n] = i;
    }
};
```



