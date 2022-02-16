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

[Back To The Top](#leetcode-solutions)
