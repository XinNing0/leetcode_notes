# 🧭 第一章：二分法（Binary Search)

> 🚀 **核心思想：**
> 在一个有序区间内，每次取中点，判断目标在左半还是右半，从而每次将搜索范围缩小一半。  
> 这种“折半”思想让查找效率从 **O(n)** 提升到 **O(log n)**。

---

## 💡 为什么使用二分法？

- 暴力解：逐个遍历 → **O(n)**  
- 二分法：每轮排除一半元素 → **O(log n)**  
- 能在**有序数组或区间问题**中大幅提高效率。

---

## 🎯 适用场景

- 区间有序（升序或降序）
- 查找：
  - 精确目标值（exact match）
  - 最左边界 / 最右边界
  - 第一个 ≥ target 或 最后一个 ≤ target

---

## 🧠 思考重点

1. **Search 区间是什么？**
   - `[start, end]`（闭区间）还是 `[start, end)`（半开区间）
   - 不同定义影响循环条件和终止判断

2. **你找的 target 是什么？**
   - 精确值  
   - 左边界 / 右边界  
   - 满足条件的最小 / 最大位置  

---

## 🐍 Python 模板（含完整注释）

```python
def search(self, nums: List[int], target: int) -> int:
    """
    二分查找模板 (Python)
    :param nums: 有序数组
    :param target: 目标值
    :return: 目标值下标，如果不存在返回 -1
    """

    # 定义左右边界
    start = 0
    end = len(nums) - 1

    # 循环条件：保证区间内至少有两个元素
    # 使用 start + 1 < end 避免死循环
    while start + 1 < end:
        # 计算中点（整除）
        mid = (start + end) // 2

        # 若中点值 < 目标，说明目标在右侧
        if nums[mid] < target:
            start = mid

        # 若中点值 > 目标，说明目标在左侧
        elif nums[mid] > target:
            end = mid

        # 若 nums[mid] == target，直接返回索引
        else:
            return mid

    # 检查剩余的两个边界
    if nums[start] == target:
        return start
    if nums[end] == target:
        return end

    # 若都不是，返回 -1 表示未找到
    return -1


## Java 模板（含完整注释）
```java 

public class BinarySearch {
    /**
     * 二分查找模板 (Java)
     * @param nums 有序数组
     * @param target 目标值
     * @return 目标索引，若不存在返回 -1
     */
    public int search(int[] nums, int target) {
        // 边界检查：数组为空或长度为 0，直接返回 -1
        if (nums == null || nums.length == 0) {
            return -1;
        }

        // 初始化左右边界
        int start = 0;
        int end = nums.length - 1;

        // 循环条件：保证至少有两个元素
        // 防止死循环，退出时 start 和 end 相邻
        while (start + 1 < end) {
            // 计算中点，避免溢出写法
            int mid = start + (end - start) / 2;

            // 若中点值 < 目标，搜索右侧
            if (nums[mid] < target) {
                start = mid;
            }
            // 若中点值 > 目标，搜索左侧
            else if (nums[mid] > target) {
                end = mid;
            }
            // 若找到目标，直接返回
            else {
                return mid;
            }
        }

        // 检查剩余的两个边界位置
        if (nums[start] == target) {
            return start;
        }
        if (nums[end] == target) {
            return end;
        }

        // 若未找到，返回 -1
        return -1;
    }

    // ✅ 测试样例
    public static void main(String[] args) {
        BinarySearch bs = new BinarySearch();
        int[] nums = {1, 3, 5, 7, 9};
        int target = 7;
        int index = bs.search(nums, target);
        System.out.println(index);  // 输出 3
    }
}

```


