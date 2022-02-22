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

Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.</br></br>You may assume that each input would have exactly one solution, and you may not use the same element twice.</br></br>You can return the answer in any order.

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

### Problem 9 - Palindrome Number

#### Question: </br>

<details>
  <summary>Click to expand</summary>
<br/>

Given an integer x, return true if x is palindrome integer.</br></br>An integer is a palindrome when it reads the same backward as forward.</br></br>For example, 121 is a palindrome while 123 is not.

</details>

#### My Solution: </br>

<details>
  <summary>Click to expand</summary>
  
```javascript
var isPalindrome = function(x) {
    
    if (x < 0) {
        return false;
    }
    
    var inputStr = x.toString();
    
    function inner(inputStr) {
        if (inputStr.length <= 1) {
            return true;
        }
        
        if (inputStr[0] === inputStr[inputStr.length - 1]) {
            return inner(inputStr.slice(1, inputStr.length - 1));
        }
        
        return false;
    }
    
    return inner(inputStr);
};

````

</details>

---

### Problem 13 - Roman To Integer

#### Question: </br>

<details>
  <summary>Click to expand</summary>
<br/>

Roman numerals are represented by seven different symbols: I, V, X, L, C, D and M.</br>

| Symbol | Value |
| :----- | :---- |
| I      | 1     |
| V      | 5     |
| X      | 10    |
| L      | 50    |
| C      | 100   |
| D      | 500   |
| M      | 1000  |

For example, 2 is written as II in Roman numeral, just two one's added together. 12 is written as XII, which is simply X + II. The number 27 is written as XXVII, which is XX + V + II.</br></br>Roman numerals are usually written largest to smallest from left to right. However, the numeral for four is not IIII. Instead, the number four is written as IV. Because the one is before the five we subtract it making four. The same principle applies to the number nine, which is written as IX. There are six instances where subtraction is used:</br>

- I can be placed before V (5) and X (10) to make 4 and 9.<br/>
- X can be placed before L (50) and C (100) to make 40 and 90. <br/>
- C can be placed before D (500) and M (1000) to make 400 and 900.

</details>

#### My Solution: </br>

<details>
  <summary>Click to expand</summary>

```javascript
var romanToInt = function (s) {
  const map = {
    I: 1,
    IV: 4,
    V: 5,
    IX: 9,
    X: 10,
    XL: 40,
    L: 50,
    XC: 90,
    C: 100,
    CD: 400,
    D: 500,
    CM: 900,
    M: 1000,
  };

  let total = 0;

  for (let i = 0; i < s.length; i++) {
    let char = s[i];

    if (s[i] === 'I' && s[i + 1] === 'V') {
      char = 'IV';
      i++;
    } else if (s[i] === 'I' && s[i + 1] === 'X') {
      char = 'IX';
      i++;
    } else if (s[i] === 'X' && s[i + 1] === 'L') {
      char = 'XL';
      i++;
    } else if (s[i] === 'X' && s[i + 1] === 'C') {
      char = 'XC';
      i++;
    } else if (s[i] === 'C' && s[i + 1] === 'D') {
      char = 'CD';
      i++;
    } else if (s[i] === 'C' && s[i + 1] === 'M') {
      char = 'CM';
      i++;
    }
    total += map[char];
  }

  return total;
};
```

</details>

---

### Problem 141 - Linked List Cycle

#### Question: </br>

<details>
  <summary>Click to expand</summary>
<br/>

Given head, the head of a linked list, determine if the linked list has a cycle in it.</br></br>There is a cycle in a linked list if there is some node in the list that can be reached again by continuously following the next pointer. Internally, pos is used to denote the index of the node that tail's next pointer is connected to. Note that pos is not passed as a parameter.</br></br>Return true if there is a cycle in the linked list. Otherwise, return false.

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

````

</details>

---

[Back To The Top](#leetcode-solutions)
