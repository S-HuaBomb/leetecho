
# 169. Majority Element - 多数元素

## Tags - 题目标签

 <img src="https://img.shields.io/badge/Array-数组-blue.svg">   <img src="https://img.shields.io/badge/Hash Table-哈希表-blue.svg">   <img src="https://img.shields.io/badge/Divide and Conquer-分治-blue.svg">   <img src="https://img.shields.io/badge/Counting-计数-blue.svg">   <img src="https://img.shields.io/badge/Sorting-排序-blue.svg">  


## Description - 题目描述

### EN:
<p>Given an array <code>nums</code> of size <code>n</code>, return <em>the majority element</em>.</p>

<p>The majority element is the element that appears more than <code>&lfloor;n / 2&rfloor;</code> times. You may assume that the majority element always exists in the array.</p>

<p>&nbsp;</p>
<p><strong>Example 1:</strong></p>
<pre><strong>Input:</strong> nums = [3,2,3]
<strong>Output:</strong> 3
</pre><p><strong>Example 2:</strong></p>
<pre><strong>Input:</strong> nums = [2,2,1,1,1,2,2]
<strong>Output:</strong> 2
</pre>
<p>&nbsp;</p>
<p><strong>Constraints:</strong></p>

<ul>
	<li><code>n == nums.length</code></li>
	<li><code>1 &lt;= n &lt;= 5 * 10<sup>4</sup></code></li>
	<li><code>-10<sup>9</sup> &lt;= nums[i] &lt;= 10<sup>9</sup></code></li>
</ul>

<p>&nbsp;</p>
<strong>Follow-up:</strong> Could you solve the problem in linear time and in <code>O(1)</code> space?

### ZH-CN:
<p>给定一个大小为 <em>n </em>的数组，找到其中的多数元素。多数元素是指在数组中出现次数 <strong>大于</strong> <code>⌊ n/2 ⌋</code> 的元素。</p>

<p>你可以假设数组是非空的，并且给定的数组总是存在多数元素。</p>

<p> </p>

<p><strong>示例 1：</strong></p>

<pre>
<strong>输入：</strong>[3,2,3]
<strong>输出：</strong>3</pre>

<p><strong>示例 2：</strong></p>

<pre>
<strong>输入：</strong>[2,2,1,1,1,2,2]
<strong>输出：</strong>2
</pre>

<p> </p>

<p><strong>进阶：</strong></p>

<ul>
	<li>尝试设计时间复杂度为 O(n)、空间复杂度为 O(1) 的算法解决此问题。</li>
</ul>



## Link - 题目链接

[LeetCode](https://leetcode.com/problems/majority-element/description/)  -  [LeetCode-CN](https://leetcode-cn.com/problems/majority-element/description/)
## Latest Accepted Submissions - 最近一次 AC 的提交


| Language | Runtime | Memory | Submission Time |
|:---:|:---:|:---:|:---:|
| javascript  | 56 ms | 36.3 MB | 2019/11/05 21:44 |

```javascript

/**
 * @param {number[]} nums
 * @return {number}
 */
var majorityElement = function(nums) {
   let count = 0;
   let candidate = null;

   nums.forEach(function(num){
        if (count == 0) {
            candidate = num;
        }
        count += (num == candidate) ? 1 : -1;
    });

    return candidate;
};

```
## My Notes - 我的笔记



No notes

