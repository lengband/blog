---
title: LeetCode
date: 2020-06-01 10:29:46
categories:
- JS
---

## 简单模式


#### 两数之和

**题目**
给定一个整数数组nums和一个目标值target，在数组中找出和为目标值的两个整数的下标
如：数组[2, 4, 7, 9, 3, 13] 和 目标值 11，4+7=11，那么应该返回 4 和 7 的下标


**解题**
一、
```javascript
const twoSum = (nums, target) => {
  // 存放出现过的数字，和对应的索引
  const prevNums = {};                         
  // 遍历元素
  for (let i = 0; i < nums.length; i++) {      
    // 当前元素
    const curNum = nums[i];                    
    // 满足题目要求的目标元素
    const targetNum = target - curNum;         
    // 在prevNums中找目标元素的索引
    const targetNumIndex = prevNums[targetNum];
    // 如果存在，直接返回 [目标元素的索引, 当前索引]
    if (targetNumIndex !== undefined) {        
      return [targetNumIndex, i];             
    }                                     
    // 如果不存在，说明之前没出现过目标元素
    // 每次都存入当前元素和对应的索引
    prevNums[curNum] = i;                      
  }
}
console.log(twoSum([2, 4, 7, 9, 3, 13], 11))
```
二、
```javascript
function twoSum (nums, target) {
  var hashTable
  if (target > 500 || target < -500) {
    hashTable = {}
  } else {
    var buffer = new ArrayBuffer(4 * 1000)
    hashTable = new Int32Array(buffer)
  }
  for (var i = 0; i < nums.length; i++) {
    var res = hashTable[target - nums[i] + 500]
    if (res) {
      return [res - 1, i]
    } else {
      hashTable[nums[i] + 500] = i + 1
    }
  }
}
console.log(twoSum([2, 4, 7, 9, 3, 13], 11))
```


#### 整数反转
**题目**
给出一个 32 位的有符号整数，你需要将这个整数中每位上的数字进行反转。

示例 1:
输入: 123
输出: 321

示例 2:
输入: -123
输出: -321

示例 3:
输入: 120
输出: 21

注意:
假设我们的环境只能存储得下 32 位的有符号整数，则其数值范围为 [−2^31, 2^31 − 1]。请根据这个假设，如果反转后整数溢出那么就返回 0。

**解题**
一、巧用按位非运算符
解题思路
* result * 10 + x % 10 取出末位 x % 10（负数结果还是负数，无需关心正负），拼接到 result 中。
* x / 10 去除末位，| 0 强制转换为32位有符号整数。
* 通过 | 0 取整，无论正负，只移除小数点部分（正数向下取整，负数向上取整）。
* result | 0 超过32位的整数转换结果不等于自身，可用作溢出判断。

运算过程:
x | result
--|-------
123 | 0
12 | 3
1 | 32
0 | 321

代码
```javascript
/**
 * @param {number} x
 * @return {number}
 */
var reverse = function(x) {
  let result = 0;
  while(x !== 0) {
    result = result * 10 + x % 10;
    x = (x / 10) | 0; // 取整
  }
  return (result | 0) === result ? result : 0; // 如果输入参数是带小数位，那么返回 0
};
console.log(reverse(123))
```
二、暴力法 字符串反转
```javascript
/**
 * @param {number} x
 * @return {number}
 */
var reverse = function(x) {
  let now = Math.abs(x).toString().split("").reverse().join("");
  if(x < 0){
    return now <= Math.pow(2,31) ? -now : 0;
  }else{
    return now < Math.pow(2,31) ? now : 0;
  }
};
console.log(reverse(123))
```

三、取余法 321=123%10 + 12%10 + 1%10
```javascript
/**
 * @param {number} x
 * @return {number}
 */
var reverse = function(x) {
  let ord = Math.abs(x);//去符号
  let now = 0;
  while(ord > 0){
    now = now * 10 + ord % 10;
    ord = Math.floor(ord / 10);
  }
  if(x < 0){
    return now <= Math.pow(2,31) ? -now : 0;
  }else{
    return now < Math.pow(2,31) ? now : 0;
  }
};
console.log(reverse(123))
```

#### 实现一个单项链表，并实现反转
**题目**
输入: 1->2->3->4->5->NULL
输出: 5->4->3->2->1->NULL

**解题**
```javascript
function LinkedList() {
    // 封装一个Node类, 用于保存每个节点信息
    function Node(element) {
      this.element = element
      this.next = null
    }
    // 链表中的属性
    this.length = 0
    this.head = null
    // 链表尾部追加元素方法
    LinkedList.prototype.append = function (element) {
        // 1.根据新元素创建节点
        var newNode = new Node(element)
        // 2.判断原来链表是否为空
        if (this.head === null) { // 链表为空
          this.head = newNode
        } else { // 链表不为空
            // 2.1.定义变量, 保存当前找到的节点
            var current = this.head
            while (current.next) {
              current = current.next
            }
            // 2.2.找到最后一项, 将其next赋值为node
            current.next = newNode
        }
        // 3.链表长度增加1
        this.length++
    }
}
```
实现反转
```javascript
function myReverse (linkedList) {
    // 1 拿到传参链表的head
    var head = linkedList.head
    // 2 边界判断 如果头结点是空 或者只有一个结点 那还反转个啥
    if(head === null || head.next === null) return linkedList
    // 3 用三个指针
    var current = head
    var pre = null 
    var next = null
    while(current != null) {
      next = current.next // 先存储next
      current.next = pre // 此时给next赋值的是上一个pre存储的值
      pre = current // 存储当前的current，给下次循环使用
      current = next // 继续下次循环
    }
    linkedList.head = pre
}
```
