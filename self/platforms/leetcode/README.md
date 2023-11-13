# Platforms
## LeetCode

### 387
- Q.**387**: First Unique Character in a String
- **Problem Statement**: [Link](https://leetcode.com/problems/first-unique-character-in-a-string/description/)
- **Description**: Given a string s, find the first non-repeating character in it and return its index. If it does not exist, return -1.
- **Constraints**: 
    - `s.length` -> $1$ to $10^5$
- **Example**:
    | Input: *String* | Output: *Integer* |
    | :---: | :---: |
    | $"leetcode"$ | $0$ |
    | $"loveleetcode"$ | $2$ |
    | $"aabb"$ | $-1$ |
- **Data Structure**: `Hashmap`
- **Logic**:
    1. Use the hashmap to store the frequency of all the elements.
    2. Traverse the hashmap. Return the first element whose frequency is 1.
- **Implementation**: [Code](./platforms/leetcode/1.java)

### 26
- Q.**26**: Remove Duplicates from Sorted Array
- **Problem Statement**: [Link](https://leetcode.com/problems/remove-duplicates-from-sorted-array/description/)
- **Description**: Given an integer array nums sorted in non-decreasing order, remove the duplicates in-place such that each unique element appears only once. The relative order of the elements should be kept the same. Then return the number of unique elements in nums. Consider the number of unique elements of nums to be k, to get accepted, you need to do the following things:
    - Change the array nums such that the first k elements of nums contain the unique elements in the order they were present in nums initially. The remaining elements of nums are not important as well as the size of nums.
    - Return k.
- **Constraints**: 
    - `nums.length` -> $1$ to $3*10^4$
    - `nums[i]` -> $-100$ to $100$
- **Example**:
    | Input: *Integer Array* | Output: *Integer, Integer Array* |
    | :---: | :---: |
    | $[1,1,2]$ | $2, [1,2,\_]$ |
    | $[0,0,1,1,1,2,2,3,3,4]$ | $5, [0,1,2,3,4,\_,\_,\_,\_,\_]$ |
- **Data Structure**: `Array`
- **Logic**:
    1. If length of array is 1, return 1.
    2. Initialize index where unique elements should be placed, `addIndex`, as `1`. It it set to 1 to accomodate the first element (at index 0) of the array.
    3. Traverse through the array in the range (0 to nums.length-2).
        1. If nums[index] is less than nums[index+1], the elements are unique. In this case, place nums[index+1] in index `addIndex`.
        2. Increment `addIndex` by 1.
    4. Return `addIndex`.
- **Implementation**: [Code](./platforms/leetcode/2.java)

### 121
- Q.**121**: Best Time to Buy and Sell Stock
- **Problem Statement**: [Link](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/description/)
- **Description**: You are given an array prices where prices[i] is the price of a given stock on the ith day. You want to maximize your profit by choosing a single day to buy one stock and choosing a different day in the future to sell that stock. Return the maximum profit you can achieve from this transaction. If you cannot achieve any profit, return `0`.
- **Constraints**: 
    - `prices.length` -> $1$ to $10^5$
    - `prices[i]` -> $1$ to $10^4$

- **Example**:
    | Input: *Integer Array* | Output: *Integer* |
    | :---: | :---: |
    | $[7,1,5,3,6,4]$ | $5$ |
    | $[7,6,4,3,1]$ | $0$ |
- **Data Structure**: `Array`
- **Logic**:
    1. Assume lowest price to be the `current price` at `day 1`.
    2. Traverse through the `price[]` array.
        1. If the `price at the current index` is less than `lowest price`, replace it.
        2. Calculate the current profit at every step. It is the difference between the `price at the current index` & the `current lowest price`.
        3. If `current profit` is higher than `highest profit`, replace it.
    3. At the end, we will have the `highest profit` we can earn, which is the value to be returned.
- **Implementation**: [Code](./platforms/leetcode/3.java)

### 1281
- Q.**1281**: Subtract the Product and Sum of Digits of an Integer
- **Problem Statement**: [Link](https://leetcode.com/problems/subtract-the-product-and-sum-of-digits-of-an-integer/)
- **Description**: Given an integer number n, return the difference between the product of its digits and the sum of its digits.
- **Constraints**: 
    - `n` -> $1$ to $10^5$
- **Example**:
    | Input: *Integer* | Output: *Integer* |
    | :---: | :---: |
    | $234$ | $15$ |
    | $4421$ | $21$ |
- **Data Structure**: `N/A`
- **Logic**:
    1. While `n` is not `0`, extract the digits one by one.
    2. Calculate the sum & product step-by-step.
    3. At the end, calculate the result, and return it.
- **Implementation**: [Code](./platforms/leetcode/4.cpp)

### 976
- Q.**976**: Largest Perimeter Triangle
- **Problem Statement**: [Link](https://leetcode.com/problems/largest-perimeter-triangle/)
- **Description**: Given an integer array nums, return the largest perimeter of a triangle with a non-zero area, formed from three of these lengths. If it is impossible to form any triangle of a non-zero area, return 0.
- **Constraints**: 
    - `nums.length` -> $3$ to $10^4$
    - `nums[i]` -> $1$ to $10^6$
- **Example**:
    | Input: *Integer Array* | Output: *Integer* |
    | :---: | :---: |
    | $[2,1,2]$ | $5$ |
    | $[1,2,1,10]$ | $0$ |
- **Data Structure**: `Vector Array`
- **Logic**:
    1. We first sort the input vector in ascending order. Then we traverse it in reverse ie from the largest element.
    2. We apply the geometry principle of the triangle: The sum of the lengths of any 2 sides of a triangle is greater than the length of the 3rd side.
    3. We check for this condition as we traverse through the vector. If it becomes true, we return the permeter of those 3 sides.
- **Implementation**: [Code](./platforms/leetcode/5.cpp)

### 1779
- Q.**1779**: Find Nearest Point That Has the Same X or Y Coordinate
- **Problem Statement**: [Link](https://leetcode.com/problems/find-nearest-point-that-has-the-same-x-or-y-coordinate/)
- **Description**: You are given two integers, x and y, which represent your current location on a Cartesian grid: (x, y). You are also given an array points where each points[i] = [ai, bi] represents that a point exists at (ai, bi). A point is valid if it shares the same x-coordinate or the same y-coordinate as your location. Return the index (0-indexed) of the valid point with the smallest Manhattan distance from your current location. If there are multiple, return the valid point with the smallest index. If there are no valid points, return -1. <br>
    `The Manhattan distance between two points (x1, y1) and (x2, y2) is abs(x1 - x2) + abs(y1 - y2).`
- **Constraints**: 
    - `points.length` -> $1$ to $10^4$
    - `points[i].length` -> $2$
    - `x`, `y`, `a`<sub>`i`</sub>, `b`<sub>`i`</sub> -> $1$ to $10^4$
- **Example**:
    | Input: *Integer, Integer, Nested Integer Array* | Output: *Integer* |
    | :---: | :---: |
    | $3, 4, [[1,2],[3,1],[2,4],[2,3],[4,4]]$ | $2$ |
    | $3, 4, [[3,4]]$ | $0$ |
    | $3, 4, [[2,3]]$ | $-1$ |
- **Data Structure**: `Vector Array`
- **Logic**:
    1. Initialise position & answer. Assume that answer is the maximum possible integer value (`INT_MAX`).
    2. Traverse through the input vector, array by array.
    3. For each array `[a,b]`, check if the point is valid, ie if `a` is equal to input `x`, or if `b` is equal to input `y`. If it is, then calculate the Manhattan distance.
    4. If the distance is less than the current answer, set the old position & answer to the current one.
- **Implementation**: [Code](./platforms/leetcode/6.cpp)

### 1822
- Q.**1822**: Sign of the Product of an Array
- **Problem Statement**: [Link](https://leetcode.com/problems/sign-of-the-product-of-an-array/)
- **Description**: There is a function `signFunc(x)` that returns:
    ```
    1, if x is positive.
    -1, if x is negative.
    0, if x is equal to 0.
    ```
    You are given an integer array nums. Let product be the product of all values in the array nums. Return `signFunc(product)`.
- **Constraints**: 
    - `nums.length` -> $1$ to $1000$
    - `nums[i]` -> $-100$ to $100$
- **Example**:
    | Input: *Integer Array* | Output: *Integer* |
    | :---: | :---: |
    | $[-1,-2,-3,-4,3,2,1]$ | $1$ |
    | $[1,5,0,2,-3]$ | $0$ |
    | $[-1,1,-1,1,-1]$ | $-1$ |
- **Data Structure**: `Array`
- **Logic**:
    1. The logic is that if the number of negative elements is `odd`, the resultant product is `negative`, otherwise `positive`.
    2. Traverse through the array.
    3. If any element is `0`, return `0`.
    4. Count all elements that are negative.
    5. At last, return `1` is the count is even, otherwise return `-1`.
- **Implementation**: [Code](./platforms/leetcode/7.cpp)

### 1502
- Q.**1502**: Can Make Arithmetic Progression From Sequence
- **Problem Statement**: [Link](https://leetcode.com/problems/can-make-arithmetic-progression-from-sequence/)
- **Description**: A sequence of numbers is called an arithmetic progression if the difference between any two consecutive elements is the same. Given an array of numbers `arr`, return `true` if the array can be rearranged to form an arithmetic progression. Otherwise, return `false`.
- **Constraints**: 
    - `arr.length` -> $2$ to $1000$
    - `arr[i]` -> $-10^6$ to $10^6$
- **Example**:
    | Input: *Integer Array* | Output: *Boolean* |
    | :---: | :---: |
    | $[3,5,1]$ | $true$ |
    | $[1,2,4]$ | $false$ |

- **Data Structure**: `Array`
- **Logic**:
    1. Sort the input array.
    2. Calculate the difference between element 0 & 1.
    3. For the rest of the elements (ie index 1 to last), check if the difference is the same as the initially calculated difference.
    4. If at any point the condition becomes false, return `false`.
    5. If the loop completes without terminating, return `true`.
- **Implementation**: [Code](./platforms/leetcode/8.py)

### 1295
- Q.**1295**: Find Numbers with Even Number of Digits
- **Problem Statement**: [Link](https://leetcode.com/problems/find-numbers-with-even-number-of-digits/)
- **Description**: Given an array nums of integers, return how many of them contain an even number of digits.
- **Constraints**: 
    - `nums.length` -> $1$ to $500$
    - `nums[i]` -> $1$ to $10^5$
- **Example**:
    | Input: *Integer Array* | Output: *Integer* |
    | :---: | :---: |
    | $[12,345,2,6,7896]$ | $2$ |
    | $[555,901,482,1771]$ | $1$ |

- **Data Structure**: `Array`
- **Logic**:
    1. Traverse through every element in the array.
    2. For each element, convert it to string using the in-built function.
    3. If it's length is even, then increment the counter.
    4. At last, return the counter.
- **Implementation**: [Code](./platforms/leetcode/9.java)

### 1672
- Q.**1672**: Richest Customer Wealth
- **Problem Statement**: [Link](https://leetcode.com/problems/richest-customer-wealth/)
- **Description**: You are given an `m x n` integer grid accounts where `accounts[i][j]` is the amount of money the `i​​​​​​​​​​​th​​​​ customer` has in the `j​​​​​​​​​​​th​​​​ bank`. Return the wealth that the richest customer has. A customer's wealth is the amount of money they have in all their bank accounts. The richest customer is the customer that has the maximum wealth.
- **Constraints**: 
    - `m` -> $1$ to $unspecified$
    - `n` -> $unspecified$ to $50$
    - `accounts[i][j]` -> $1$ to $100$
- **Example**:
    | Input: *Nested Integer Array* | Output: *Integer* |
    | :---: | :---: |
    | $[[1,2,3],[3,2,1]]$ | $6$ |
    | $[[1,5],[7,3],[3,5]]$ | $10$ |
    | $[[2,8,7],[7,1,3],[1,9,5]]$ | $17$ |
- **Data Structure**: `Array`
- **Logic**:
    1. Traverse through every element in the array.
    2. For each element, convert it to string using the in-built function.
    3. If it's length is even, then increment the counter.
    4. At last, return the counter.
- **Implementation**: [Code](./platforms/leetcode/10.java)

### 1
- Q.**1**: Two Sum
- **Problem Statement**: [Link](https://leetcode.com/problems/two-sum/)
- **Description**: Given an array of integers `nums` and an integer `target`, return indices of the two numbers such that they add up to `target`. You may assume that each input would have exactly one solution, and you may not use the same element twice. You can return the answer in any order.
- **Constraints**: 
    - `nums.length` -> $2$ to $10^4$
    - `nums[i]` -> $-10^9$ to $10^9$
    - `target` -> $-10^9$ to $10^9$
- **Example**:
    | Input: *Integer Array, Integer* | Output: *Integer Array* |
    | :---: | :---: |
    | $[2,7,11,15], 9$ | $[0,1]$ |
    | $[3,2,4], 6$ | $[1,2]$ |
    | $[3,3], 6$ | $[0,1]$ |
- **Data Structure**: `Array`
- **Logic**:
    1. We check every element with every other element for the condition. Element `0` is paired with element `1` to `last`, element `1` is paired with elements `2` to `last`, etc.
    2. We run 2 loops to accomplish the task.
    3. We also avoid checking the elements in the same index (`0` with `0`, or `1` with `1`) by performing a check prior to evaluating them.
- **Implementation**: [Code](./platforms/leetcode/11.java)

### 9
- Q.**9**: Palindrome Number
- **Problem Statement**: [Link](https://leetcode.com/problems/palindrome-number/)
- **Description**: Given an integer `x`, return `true` if `x` is a palindrome, and `false` otherwise.
- **Constraints**: 
    - `x` -> $-2^{31}$ to $2^{31}-1$
- **Example**:
    | Input: *Integer* | Output: *Boolean* |
    | :---: | :---: |
    | $121$ | $true$ |
    | $-121$ | $false$
    | $10$ | $false$
- **Data Structure**: `String`
- **Logic**:
    1. Convert the input integer to a string using the in-built function.
    2. Setup 2 pointers, one traversing the input from the beginning (`head`), the other from the end (`tail`).
    3. While traversing, at any point, if the character at `head` found to be different from the character at `tail`, it means the string isn't palindrome. In that case, return `false` immediately and exit.
    4. If the for loop completes without terminating, return `true`.
- **Implementation**: [Code](./platforms/leetcode/12.java)

### 26
- Q.**26**: Remove Duplicates from Sorted Array
- **Problem Statement**: [Link](https://leetcode.com/problems/remove-duplicates-from-sorted-array/)
- **Description**: Given an integer array nums sorted in non-decreasing order, remove the duplicates in-place such that each unique element appears only once. The relative order of the elements should be kept the same. Then return the number of unique elements in nums. <br>
    Consider the number of unique elements of nums to be `k`, to get accepted, you need to do the following things: Change the array nums such that the first `k` elements of nums contain the unique elements in the order they were present in nums initially. The remaining elements of nums are not important as well as the size of nums. Return k.
- **Constraints**: 
    - `nums.length` -> $1$ to $3*10^4$
    - `nums[i]`-> $-100$ to $100$
    - `nums` is sorted in **ascending** order.
- **Example**:
    | Input: *Integer* | Output: *Boolean* |
    | :---: | :---: |
    | $[1,1,2]$ | $2, [1,2,\_]$ |
    | $[0,0,1,1,1,2,2,3,3,4]$ | $5, [0,1,2,3,4,\_,\_,\_,\_,\_]$ |
- **Data Structure**: `Array`
- **Logic**:
    1. EDGE Case: If length of the array is 1, no duplicates exist.
    2. Initialize the index to add elements, `addIndex`, as 1.    1. Run a loop through the sorted input array.
    3. If the $i^{th}$ element is same as the $(i+1)^{th}$ element, `addIndex` stays in the location of the 1st instance of the duplicate element. Meanwhile, we keep incrementing the `i`.
    4. The first iteration where $i^{th}$ element becomes less than the $(i+1)^{th}$ element, we replace the larger element `nums[i+1]` with the duplicate element in location `addIndex`.
- **Implementation**: [Code](./platforms/leetcode/13.java)

### 605
- Q.**605**: Can Place Flowers
- **Problem Statement**: [Link](https://leetcode.com/problems/can-place-flowers/)
- **Description**: You have a long flowerbed in which some of the plots are planted, and some are not. However, flowers cannot be planted in adjacent plots. Given an integer array flowerbed containing 0's and 1's, where 0 means empty and 1 means not empty, and an integer n, return `true` if `n` new flowers can be planted in the flowerbed without violating the no-adjacent-flowers rule and `false` otherwise.
- **Constraints**: 
    - `flowerbed.length` -> $1$ to $2*10^4$
    - `flowerbed[i]`-> $0$ or $1$
    - There are no adjacent flowers in `flowerbed`.
    - `n` -> $0$ to $flowerbed.length$
- **Example**:
    | Input: *Integer Array, Integer* | Output: *Boolean* |
    | :---: | :---: |
    | $[1,0,0,0,1], 1$ | $true$ |
    | $[1,0,0,0,1], 2$ | $false$ |
- **Data Structure**: `Array`
- **Logic**:
    1. Traverse through the input array.
        1. If any one of these conditions is true, the flower can be planted in the current `index`.
        2. If a flower is not present already.
        3. If there are no flowers before `index` **and** (if index **either** points to the `last element` **or** there are no flowers just after it).
        4. In the last point, 2 checks are needed in the 2nd part because if `index` points to the last element, `flowerbed[index+1]` is going to return an `ArrayIndexOutOfBoundsException`.
    2. If a flower can be planted, plant it. Decrease `n` by `1`, because 1 flower has already been planted.
- **Implementation**: [Code](./platforms/leetcode/14.java)

<!-- ### 1523
- Q.**1523**: Count Odd Numbers in an Interval Range
- **Problem Statement**: [Link](https://leetcode.com/problems/count-odd-numbers-in-an-interval-range/)
- **Description**: Given a string s, find the first non-repeating character in it and return its index. If it does not exist, return -1.
- **Data Structure**: `Hashmap`
- **Logic**:
    1. Use the hashmap to store the frequency of all the elements.
    2. Traverse the hashmap. Return the first element whose frequency is 1.
- **Implementation**: [Code](./platforms/leetcode/1.cpp) -->