# 🎯 LeetCode 刷题与复习追踪器 (Top K 专题)

> **当前进度：** 3 / 6
> **最后更新：** 2026-03-03

| 题号 | 题目 (点击跳转) | 难度 | 状态 | 初刷日期 | 复习1 (3D) | 复习2 (7D) | 复习3 (30D) | 笔记链接 |
| :--- | :--- | :---: | :---: | :--- | :--- | :--- | :--- | :--- |
| 215 | [Kth Largest Element](https://leetcode.cn/problems/kth-largest-element-in-an-array/) | 🟡 | 🟢 | 03-01 | [x] 03-04 | [ ] 03-08 | [ ] 04-01 | [跳转](#215-kth-largest-element-in-an-array) |
| 347 | [Top K Frequent](https://leetcode.cn/problems/top-k-frequent-elements/) | 🟡 | 🟢 | 03-01 | [x] 03-04 | [ ] 03-08 | [ ] 04-01 | [跳转](#347-top-k-frequent-elements) |
| 973 | [K Closest Points](https://leetcode.cn/problems/k-closest-points-to-origin/) | 🟡 | 🟡 | 03-03 | [ ] 03-06 | [ ] 03-10 | [ ] 04-02 | [跳转](#973-k-closest-points-to-origin) |
| 692 | [Top K Frequent Words](https://leetcode.cn/problems/top-k-frequent-words/) | 🟡 | ⚪ | 待定 | [ ] | [ ] | [ ] | [跳转](#692-top-k-frequent-words) |
| 23 | [Merge k Sorted Lists](https://leetcode.cn/problems/merge-k-sorted-lists/) | 🔴 | ⚪ | 待定 | [ ] | [ ] | [ ] | [跳转](#23-merge-k-sorted-lists) |
| 295 | [Find Median](https://leetcode.cn/problems/find-median-from-data-stream/) | 🔴 | ⚪ | 待定 | [ ] | [ ] | [ ] | [跳转](#295-find-median-from-data-stream) |

---

## 📝 详细感想与核心笔记

### 215. Kth Largest Element in an Array
* **核心思路：** 维持大小为 $K$ 的小顶堆。
* **我的感想：** 刷题的起点。理解了“找大用小”的逻辑：因为堆顶是最小值，只要新元素比堆顶大，就踢掉堆顶，剩下的就是最大的 $K$ 个。

### 347. Top K Frequent Elements
* **核心思路：** `HashMap` 计数 + 小顶堆。
* **我的感想：** 第一次处理频率问题。学会了将 `Map.Entry` 放入堆中，或者将 `int[] {num, count}` 放入堆中的技巧。

### 973. K Closest Points to Origin
* **核心思路：** 大顶堆维持 $K$ 个最小距离。
* **我的感想：** * 💡 **新姿势**：`PriorityQueue<int[]>` 存储坐标非常简洁，省去了写自定义 Pair 类的繁琐。
    * ⚠️ **易错点**：求最近（最小）要用**大顶堆**来淘汰远（大）的。
    * 🚀 **优化**：直接比较 $x^2 + y^2$，避开 `Math.sqrt` 提升性能。

### 692. Top K Frequent Words
* **核心思路：** 堆 + 复杂的 Comparator。
* **待记录：** (待初刷后更新感悟)

### 23. Merge k Sorted Lists
* **核心思路：** 多路归并。
* **待记录：** (待初刷后更新感悟)

### 295. Find Median from Data Stream
* **核心思路：** 对顶堆。
* **待记录：** (待初刷后更新感悟)