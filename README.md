# LeetCode Solutions

---

## Description

My answers for the LeetCode althorigthm challenges [leetcode.com](https://leetcode.com/)

---

## Problems

### Problem 1 - Two Sum

#### Question: </br>

<details>
  <summary>Click to expand</summary>
<br/>

> Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.</br></br>You may assume that each input would have exactly one solution, and you may not use the same element twice.</br></br>You can return the answer in any order.

</details>

#### My Solution: </br>

<details>
  <summary>Click to expand</summary>
  
```javascript
const twoSum = (nums, target) => {
  for (let i = 0; i < nums.length; i++) {
      for (let j = i + 1; j < nums.length; j++) {
        if (nums[i] + nums[j] === target) {
          return [i, j];
        }
      }
   }
};

````
</details>

#### 0(n) solution (found in discussion section): </br>

<details>
  <summary>Click to expand</summary>

```javascript
const twoSum = (nums, target) => {
  let map = {};

  for (let i = 0; i < nums.length; ++i) {
    const num = nums[i];
    const diff = target - num;

    if (diff in map) {
      return [map[diff], i];
    } else {
      map[nums[i]] = i;
    }
  }
};

twoSum([9, 2, 11, 5, 8], 7);

````

</details>

---

### Problem 141 - Linked List Cycle

#### Question: </br>

<details>
  <summary>Click to expand</summary>
<br/>

> Given head, the head of a linked list, determine if the linked list has a cycle in it.</br></br>There is a cycle in a linked list if there is some node in the list that can be reached again by continuously following the next pointer. Internally, pos is used to denote the index of the node that tail's next pointer is connected to. Note that pos is not passed as a parameter.</br></br>Return true if there is a cycle in the linked list. Otherwise, return false.

</details>

#### My Solution: </br>

<details>
  <summary>Click to expand</summary>
  
```javascript
var hasCycle = function(head) {
    if (!head) {
        return false;
    }
    
    var slow = head;
    var fast = head.next;
    
    while (fast !== null) {
        if (fast.next !== null) {
            fast = fast.next;    
        } else {
            return false;
        }
        
        if (fast === slow) {
            return true;
        }
        slow = slow.next;
        fast = fast.next;
    }
    
    return false;
};

```

</details>

---

[Back To The Top](#leetcode-solutions)
```
