# 3. 无重复字符的最长子串 - Solution

## 题目描述

给定一个字符串 `s`，请你找出其中不含有重复字符的 **最长子串** 的长度。

## 解法思路

### 滑动窗口法
1. **初始化**：使用哈希集合 (`unordered_set`) 记录当前窗口中的字符，维护窗口的左右指针 `left` 和 `right`。
2. **移动右指针**：
   - 如果 `s[right]` 不在集合中，将其加入集合，并更新最大长度。
   - 如果 `s[right]` 在集合中，移动 `left` 指针，直到窗口内无重复字符。
   



### 优化思路
- 用哈希映射 (`unordered_map`) 直接记录字符的最新索引，将 `left` 跳跃式移动至 `max(left, map[s[right]] + 1)`，避免逐字符移动。

## 复杂度分析

时间复杂度：$O(n)$  
空间复杂度：$O(min(m,n))$，其中m为字符集大小  
