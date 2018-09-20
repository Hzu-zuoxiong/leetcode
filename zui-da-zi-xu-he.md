# 最大子序和

给定一个整数数组`nums` ，找到一个具有最大和的连续子数组（子数组最少包含一个元素），返回其最大和。

**示例:**

```
输入:
 [-2,1,-3,4,-1,2,1,-5,4],
输出:
 6
 
解释:
 连续子数组 [4,-1,2,1] 的和最大，为 6。
```

**进阶:**

如果你已经实现复杂度为 O\(_n_\) 的解法，尝试使用更为精妙的分治法求解。

---

## AC代码：

```js
/**
 * @param {number[]} nums
 * @return {number}
 */
var maxSubArray = function(nums) {    
    let sum = 0, max = nums[0];
    for(let i = 0; i < nums.length; i++) {
        sum += nums[i];
        if(sum < nums[i]) {
            sum = nums[i];
        }
        if(sum > max) {
            max = sum;
        }
    }
    return max;
};

// 使用JS的reduce解法。
var maxSubArray = function(nums) {
    let max = nums[0];
    
    nums.reduce((sum, num) => {
        sum = Math.max(sum + num, num);
        max = Math.max(sum, max);
        return sum;
    });
    return max;
};
```


