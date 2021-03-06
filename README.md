# data-structure-and-algorithm-with-javascript

## Table of Contents

1. [Time Comlexity](#time-complexity)
2. [Space complexity](#space-complexity)
3. [Warm up Problems](#wram-up-problems)
    - [FizzBuzz](#fizzbuzz)
    - [Swap Variables](#swap-variables)
    - [Reverse String](#reverse-string)
    - [Reverse Number](#reverse-number)
    - [Remove Duplicate](#remove-duplicate)
4. [Algorithm](#algorithm)
    - [Factorial](#factorial)
    - [Fibonacci](#fibonacci)
    - [Check Prime Number](#check-prime-number)
    - [Linear Search](#linear-search)
    - [Binary Search](#binary-search)
    - [Selection Sort](#selection-sort)
    - [Bubble Sort](#bubble-sort)
5. [Data Structure](#data-structure)
    - [Stack](#stack)
    - [Queue](#queue)

## Time Complexity
```javascript
// time complexity O(1)
const n = 10;
const m = 20;
const x = m + n;
console.log(x);

// time complexity 0(1)
const total = n * (n + 1) / 2;
console.log(total);

// time complexity O(n2)
const input = 10;
let total = 0;
for (let i = 1; i <= input; i++) {
    total += i;
}
console.log(total);

// time complexity O(n3)
const input = 10;
for (let i = 0; i < input; i++) {
    for (let j = 0; j < input; j++) {
        console.log(j);
    }
}
```

## Space Complexity
```javascript
const nums = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
const evenNums = [];
for (let i = 0; i < nums.length; i++) {
    if (nums[i] % 2 === 0) {
        evenNums.push(nums[i]);
    }
}
console.log(evenNums); // output: [2, 4, 6, 8, 10]
```
**[⬆ back to top](#table-of-contents)**

# Warm up Problems
## FizzBuzz
```javascript
const fizzBuzz = num => {
    for (let i = 0; i < num; i++) {
        if (i % 3 === 0 && i % 5 === 0) {
            console.log("FizzBuzz");
        } else if (i % 3 === 0) {
            console.log("Fizz");
        } else if (i % 5 === 0) {
            console.log("Buzz");
        } else {
            console.log(i);
        }
    }
}
console.log(fizzBuzz(15));
```
## Swap Variables 
```javascript
let a = 10;
let b = 20;
let temp = a;
a = b;
b = temp;
console.log(a, b); // 20 10

// or 
let x = 5;
let y = 10;
x = x + y;
y = x - y;
x = x - y;
console.log(x, b);  // 10 5

// or
let m = 100;
let n = 200;
[m, n] = [n, m]
console.log(m, n); // 200 100
```
**[⬆ back to top](#table-of-contents)**

## Reverse String 
```javascript
const reverseString = string => {
    return string.split("").reverse().join("");
}
console.log(reverseString("Hello World"));
// output: dlroW olleH
```
## Reverse Number 
```javascript
const reverseNumber = num => {
    const reverse = num.toString().split('').reverse().join('');
    return parseInt(reverse) * Math.sign(num);
}
console.log(reverseNumber(-20)); // output: -2
```

## Remove Duplicate
```javascript
const removeDuplicate = inputArr => {
    const uniqueArr = [];
    for (let i = 0; i < inputArr.length; i++) {
        let element = inputArr[i];
        if (!uniqueArr.includes(element)) {
            uniqueArr.push(element);
        }
    }
    return uniqueArr;
}
console.log(removeDuplicate([22, 32, 44, 22, 32]));
// output: [22, 32, 44]
```

**[⬆ back to top](#table-of-contents)**

# Algorithm
## Factorial
```javascript
// Using for Loop
const factorial = num => {
    let factNum = 1;
    for (let i = 1; i <= num; i++) {
        factNum *= i;
    }
    return factNum;
}
console.log(factorial(5)); // output: 120

// Using Recursive
const factorial = num => {
    if (num === 0) {
        return 1;
    }
    return num * factorial(num - 1);
}
console.log(factorial(5)); // output: 120
```

## Fibonacci
```javascript
// Using for Loop
const fibonacci = num => {
    const fibo = [1, 2];
    for (let i = 2; i < num - 1; i++) {
        fibo[i] = fibo[i - 1] + fibo[i - 2];
    }
    return fibo;
}
console.log(fibonacci(10));
// output: [1, 2, 3, 5, 8, 13, 21, 34, 55]

// Using Recursive
const fibonacci = num => {
    if (num === 0) {
        return 0;
    }
    if (num === 1) {
        return 1;
    }
    return fibonacci(num - 1) + fibonacci(num - 2);
}
console.log(fibonacci(10)); // output: 55
```
## Check Prime Number 
```javascript
const checkPrime = num => { 
    let isPrime = true;
    for (let i = 2; i < num; i++) { 
        if (num % i == 0) { 
            isPrime = false;
            break;
        }
    }
    return isPrime;
}
console.log(checkPrime(2));
```
**[⬆ back to top](#table-of-contents)**

## Linear Search

```javascript
// Implementing Linear Search
const nums = [12, 5, 22, 14, 10, 89, 65, 34]
const n = 65;
const linearSearch = (inputArr, element) => {
    for (let i = 0; i < inputArr.length; i++) {
        if (inputArr[i] === element) {
            return i;
        }
    }
    return -1;
}
linearSearch(nums, n); // output: 6

// Implementing Linear Search by JS Built-in Method
nums.indexOf(n); // output: 6
// or
nums.includes(n); // It returns true/false - output: true
```

## Binary Search
```javascript
// Implementing Binary Search
const nums = [23, 34, 54, 65, 76, 87, 95, 99, 120, 150]
const binarySearch = (inputArr, element) => {
    let leftNodeIndex = 0;
    let rightNodeIndex = inputArr.length - 1;

    while (leftNodeIndex <= rightNodeIndex) {
        let midNode = Math.floor((leftNodeIndex + rightNodeIndex) / 2);

        if (inputArr[midNode] === element) {
            return midNode;
        }
        if (inputArr[midNode] < element) {
            leftNodeIndex = midNode + 1;
        } else {
            rightNodeIndex = midNode - 1;
        }
    }
    return -1;
}
console.log(binarySearch(nums, 65));  // output: 3
```
**[⬆ back to top](#table-of-contents)**

## Selection Sort
```javascript
// Implementing Selection Sort
const nums = [87, 43, 32, 33, 2, 20, 22];

const selectionSort = arr => {
    const len = arr.length;
    for (let i = 0; i < len; i++) {
        let min = i;
        for (let j = min + 1; j < len; j++) {
            if (arr[min] > arr[j]) {
                min = j;
            }
        }

        if (min !== i) {
            [arr[i], arr[min]] = [arr[min], arr[i]];
        }
    }
    return arr;
}
console.log(selectionSort(nums)) // output: [2, 20, 22, 32, 33, 43, 87]
```
## Bubble Sort
```javascript
// Implementing Selection Sort
const nums = [87, 43, 32, 33, 2, 20, 22];

const bubbleSort = inputArr => {
    let len = inputArr.length;
    for (let i = 0; i < len; i++) {

        for (let j = 0; j < len; j++) {
            if (inputArr[j] > inputArr[j + 1]) {
                [ inputArr[j], inputArr[j + 1] ] = [ inputArr[j + 1], inputArr[j] ]
            }
        }

    }
    return inputArr;
};
console.log(bubbleSort(nums)); // output: [2, 20, 22, 32, 33, 43, 87]
```
**[⬆ back to top](#table-of-contents)**

# Data Structure

## Stack
```javascript
// Simple Implementation
const stack = [];
stack.push(42);
stack.push(22);
console.log(stack); // expected output: [ 42, 22 ]
stack.pop();
console.log(stack); // expected output: [ 42 ]

// Implementing Stack using Class
class Stack {
    constructor () {
        this.stack = [];
    }
    push (value) {
        this.stack.push(value);
    }
    pop () {
        return this.stack.pop();
    }
    // peek() is used for showing the last element of the Stack. Can skip it.
    peek () {
        return this.stack[ this.stack.length - 1 ]
    } 
}
const myStack = new Stack();
myStack.push(55);
myStack.push(66);
console.log(myStack); 
//expected output: Stack Stack { stack: [ 55, 66 ] }
myStack.pop();
console.log(myStack); 
// expected output: Stack { stack: [ 55 ] }
```

## Queue
```javascript
// Simple Implementation
const queue = []
queue.unshift(32);
queue.unshift(22);
console.log(queue); // expected output: [ 22, 32 ]
queue.pop()
console.log(queue);  // expected output: [ 22 ]

// Implementing Queue using Class
class Queue {
    constructor () {
        this.queue = [];
    }
    enQueue (value) {
        this.queue.unshift(value);
    }
    deQueue () {
        return this.queue.pop();
    }
    peek () {
        return this.queue[this.queue.length - 1]
    }
}
const myQueue = new Queue();
myQueue.enQueue(11);
myQueue.enQueue(22);
console.log(myQueue); 
//expected output: Queue { queue: [ 22, 11 ] }
myQueue.deQueue();
console.log(myQueue); 
// expected output: Queue { queue: [ 22 ] }
```
**[⬆ back to top](#table-of-contents)**