# leet-day52

# Linked List Cycle

## Problem Description

Given the `head` of a linked list, determine if the linked list has a cycle in it. A cycle exists in a linked list if there is a node in the list that can be reached again by continuously following the `next` pointer. The problem includes the definition of a cycle as a circular connection of the `tail` node to a previous node.

You need to return `true` if there is a cycle in the linked list; otherwise, return `false`.

## Example

**Input**:
```cpp
head = [3,2,0,-4], pos = 1
```

**Output**:
```cpp
true
```

**Explanation**: There is a cycle in the linked list, where the `tail` connects to the 1st node (0-indexed).

## Constraints

- The number of nodes in the list is in the range `[0, 10^4]`.
- `-10^5 <= Node.val <= 10^5`
- `pos` is either `-1` or a valid index in the linked list.

## Approach

To determine if there is a cycle in the linked list, we can use two pointers: `slow` and `fast`. The `slow` pointer moves one step at a time, while the `fast` pointer moves two steps at a time. If there is no cycle, the `fast` pointer will reach the end of the list (i.e., become `nullptr`). If there is a cycle, the `fast` pointer will eventually catch up to the `slow` pointer, and we return `true`. If we reach the end of the list without finding a cycle, we return `false`.

## Pseudocode

1. Initialize two pointers, `slow` and `fast`, both pointing to the `head` of the linked list.
2. While `fast` and `fast->next` are not `nullptr`, do the following:
   - Move `slow` one step forward: `slow = slow->next`
   - Move `fast` two steps forward: `fast = fast->next->next`
   - If `slow` and `fast` meet (i.e., `slow == fast`), return `true` (there is a cycle).
3. If the loop exits, return `false` (there is no cycle).

## Complexity Analysis

- Time complexity: `O(n)` - We traverse the linked list with `n` nodes once.
- Space complexity: `O(1)` - We use only a constant amount of extra space for the two pointers.

---
