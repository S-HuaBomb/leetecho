
# 1008. Construct Binary Search Tree from Preorder Traversal - 前序遍历构造二叉搜索树

## Tags - 题目标签

 <img src="https://img.shields.io/badge/Stack-栈-blue.svg">   <img src="https://img.shields.io/badge/Tree-树-blue.svg">   <img src="https://img.shields.io/badge/Binary Search Tree-二叉搜索树-blue.svg">   <img src="https://img.shields.io/badge/Array-数组-blue.svg">   <img src="https://img.shields.io/badge/Binary Tree-二叉树-blue.svg">   <img src="https://img.shields.io/badge/Monotonic Stack-单调栈-blue.svg">  


## Description - 题目描述

### EN:
<p>Given an array of integers preorder, which represents the <strong>preorder traversal</strong> of a BST (i.e., <strong>binary search tree</strong>), construct the tree and return <em>its root</em>.</p>

<p>It is <strong>guaranteed</strong> that there is always possible to find a binary search tree with the given requirements for the given test cases.</p>

<p>A <strong>binary search tree</strong> is a binary tree where for every node, any descendant of <code>Node.left</code> has a value <strong>strictly less than</strong> <code>Node.val</code>, and any descendant of <code>Node.right</code> has a value <strong>strictly greater than</strong> <code>Node.val</code>.</p>

<p>A <strong>preorder traversal</strong> of a binary tree displays the value of the node first, then traverses <code>Node.left</code>, then traverses <code>Node.right</code>.</p>

<p>&nbsp;</p>
<p><strong>Example 1:</strong></p>
<img alt="" src="https://assets.leetcode.com/uploads/2019/03/06/1266.png" style="height: 386px; width: 590px;" />
<pre>
<strong>Input:</strong> preorder = [8,5,1,7,10,12]
<strong>Output:</strong> [8,5,10,1,7,null,12]
</pre>

<p><strong>Example 2:</strong></p>

<pre>
<strong>Input:</strong> preorder = [1,3]
<strong>Output:</strong> [1,null,3]
</pre>

<p>&nbsp;</p>
<p><strong>Constraints:</strong></p>

<ul>
	<li><code>1 &lt;= preorder.length &lt;= 100</code></li>
	<li><code>1 &lt;= preorder[i] &lt;= 1000</code></li>
	<li>All the values of <code>preorder</code> are <strong>unique</strong>.</li>
</ul>


### ZH-CN:
<p>给定一个整数数组，它表示BST(即 <strong>二叉搜索树</strong> )的 <strong>先</strong><strong>序遍历</strong> ，构造树并返回其根。</p>

<p><strong>保证</strong> 对于给定的测试用例，总是有可能找到具有给定需求的二叉搜索树。</p>

<p><strong>二叉搜索树</strong> 是一棵二叉树，其中每个节点，&nbsp;<code>Node.left</code>&nbsp;的任何后代的值 <strong>严格小于</strong> <code>Node.val</code>&nbsp;,&nbsp;<code>Node.right</code>&nbsp;的任何后代的值 <strong>严格大于</strong> <code>Node.val</code>。</p>

<p>二叉树的 <strong>前序遍历</strong> 首先显示节点的值，然后遍历<code>Node.left</code>，最后遍历<code>Node.right</code>。</p>

<p>&nbsp;</p>

<p><strong>示例 1：</strong></p>

<p><img src="https://assets.leetcode.com/uploads/2019/03/06/1266.png" /></p>

<pre>
<strong>输入：</strong>preorder = [8,5,1,7,10,12]
<strong>输出：</strong>[8,5,10,1,7,null,12]
</pre>

<p><strong>示例 2:</strong></p>

<pre>
<strong>输入:</strong> preorder = [1,3]
<strong>输出:</strong> [1,null,3]
</pre>

<p>&nbsp;</p>

<p><strong>提示：</strong></p>

<ul>
	<li><code>1 &lt;= preorder.length &lt;= 100</code></li>
	<li><code>1 &lt;= preorder[i]&nbsp;&lt;= 10^8</code></li>
	<li><code>preorder</code> 中的值 <strong>互不相同</strong></li>
</ul>

<p>&nbsp;</p>



## Link - 题目链接

[LeetCode](https://leetcode.com/problems/construct-binary-search-tree-from-preorder-traversal/description/)  -  [LeetCode-CN](https://leetcode-cn.com/problems/construct-binary-search-tree-from-preorder-traversal/description/)
## Latest Accepted Submissions - 最近一次 AC 的提交


| Language | Runtime | Memory | Submission Time |
|:---:|:---:|:---:|:---:|
| python3  | 60 ms | 12.8 MB | 2019/03/13 12:11 |

```python3

# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, x):
#         self.val = x
#         self.left = None
#         self.right = None

class Solution:
    def bstFromPreorder(self, preorder: List[int]) -> TreeNode:
        root = TreeNode(preorder.pop(0))
        q = [root]
        while len(preorder):
            node = TreeNode(preorder.pop(0))
            if node.val < q[-1].val:
                q[-1].left = node
                q.append(node)
            else:
                per = q.pop()
                while len(q):
                    pa = q.pop()
                    if node.val < pa.val:
                        q.append(pa)
                        per.right = node
                        break
                    per = pa
                if len(q) == 0:
                    per.right = node
                q.append(node)
        return root
        

```
## My Notes - 我的笔记





