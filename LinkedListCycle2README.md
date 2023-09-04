# leet-day52

# Linked List Cycle Detection - Find the Starting Node of a Cycle

## Problem Description

Given a linked list, determine if it has a cycle. If a cycle exists, find the starting node of the cycle. If there is no cycle, return `null`.

## Problem Statement

You are given the head of a linked list. The linked list may or may not have a cycle. If there is a cycle, you need to find the starting node of the cycle. 

A cycle in a linked list means that there is some node in the list that can be reached again by continuously following the `next` pointer. 

## Example

**Input**:

```
Head of Linked List: [3,2,0,-4]
Position of Cycle Start: 1 (0-indexed)
```

**Output**:

```
Starting Node of Cycle: Node with value 2
```

**Explanation**:

In this example, there is a cycle in the linked list, and it starts at the node with value 2.

## Constraints

- The number of nodes in the list is in the range [0, 10^4].
- Node values are in the range [-10^5, 10^5].
- The position of the cycle (if it exists) is -1 or a valid index in the linked list.

## Approach

We can use Floyd's Tortoise and Hare algorithm to solve this problem.

1. Initialize two pointers, `slow` and `fast`, both starting at the head of the linked list.

2. Traverse the linked list using a loop where `slow` moves one step at a time, and `fast` moves two steps at a time.

3. If there is no cycle, the `fast` pointer will eventually reach the end of the list (i.e., become `null`), and we can return `null` as there is no cycle.

4. If there is a cycle, the `slow` and `fast` pointers will meet at some point within the cycle. This is because the `fast` pointer moves twice as fast as the `slow` pointer.

5. Once they meet, we reset one of the pointers to the head of the linked list (e.g., `slow`), and then move both pointers one step at a time until they meet again. The meeting point is the starting node of the cycle.

6. Return the starting node.

## Complexity Analysis

- Time complexity: O(n), where n is the number of nodes in the linked list.
- Space complexity: O(1), as we use a constant amount of extra space for the two pointers.

## Summary

This algorithm allows us to efficiently detect cycles in linked lists and find the starting node of a cycle if one exists. It uses a two-pointer approach to achieve this in linear time complexity.

---
