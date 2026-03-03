# 🎯 LeetCode 刷题与复习追踪器 (Top K 专题)

> **当前进度：** 3 / 6
> **最后更新：** 2026-03-03

| 题号 | 题目 (LeetCode.com) | 难度 | 状态 | 初刷日期 | 复习1 (3D) | 复习2 (7D) | 复习3 (30D) | 笔记链接 |
| :--- | :--- | :---: | :---: | :--- | :--- | :--- | :--- | :--- |
| 215 | [Kth Largest Element](https://leetcode.com/problems/kth-largest-element-in-an-array/) | 🟡 | 🟢 | 03-01 | [x] 03-04 | [ ] 03-08 | [ ] 04-01 | [Jump](#215-kth-largest-element-in-an-array) |
| 347 | [Top K Frequent](https://leetcode.com/problems/top-k-frequent-elements/) | 🟡 | 🟢 | 03-01 | [x] 03-04 | [ ] 03-08 | [ ] 04-01 | [Jump](#347-top-k-frequent-elements) |
| 973 | [K Closest Points](https://leetcode.com/problems/k-closest-points-to-origin/) | 🟡 | 🟡 | 03-03 | [ ] 03-06 | [ ] 03-10 | [ ] 04-02 | [Jump](#973-k-closest-points-to-origin) |
| 692 | [Top K Frequent Words](https://leetcode.com/problems/top-k-frequent-words/) | 🟡 | ⚪ | 待定 | [ ] | [ ] | [ ] | [Jump](#692-top-k-frequent-words) |
| 23 | [Merge k Sorted Lists](https://leetcode.com/problems/merge-k-sorted-lists/) | 🔴 | ⚪ | 待定 | [ ] | [ ] | [ ] | [Jump](#23-merge-k-sorted-lists) |
| 295 | [Find Median](https://leetcode.com/problems/find-median-from-data-stream/) | 🔴 | ⚪ | 待定 | [ ] | [ ] | [ ] | [Jump](#295-find-median-from-data-stream) |

---

## 📝 详细感想与核心笔记

### 215. Kth Largest Element in an Array
* **核心思路：** Maintain a **Min-Heap** of size $K$.
* **我的感想：** 理解了“找大用小”的逻辑：堆顶是最小值，新元素比堆顶大时踢掉旧堆顶，最后剩下的就是 Top K Largest。

### 347. Top K Frequent Elements
* **核心思路：** `HashMap` for counting + **Min-Heap**.
* **我的感想：** 学会了直接将 `int[] {num, count}` 放入堆中比较 `index 1` 的技巧，代码更简洁，不需要 Entry 类。

### 973. K Closest Points to Origin
* **核心思路：** Maintain a **Max-Heap** of size $K$ to keep the smallest distances.
* **我的感想：** * 💡 **新姿势**：`PriorityQueue<int[]>` 直接存坐标数组，非常省事。
    * ⚠️ **易错点**：求 Smallest $K$ 要用 **Max-Heap**（为了 poll 掉那个最大的）。
    * 🚀 **优化**：直接比较 $x^2 + y^2$ 避免 `Math.sqrt()`。
    * **进阶 (Quickselect):** 掌握了平均时间复杂度 $O(N)$ 的分区算法，面试加分项。

### 692. Top K Frequent Words
* **核心思路：** Min-Heap + Custom Comparator.
* **待记录：** 注意频率相同时，字母序（Lexicographical order）的处理。

### 23. Merge k Sorted Lists
* **核心思路：** Multi-way Merge using a Min-Heap.
* **待记录：** 每次从堆中取出最小节点，并将其 `next` 指针指向的节点重新放入堆中。

### 295. Find Median from Data Stream
* **核心思路：** Two Heaps (Max-Heap for left half, Min-Heap for right half).
* **待记录：** 核心在于保持两个堆的平衡（size 差不超过 1）。