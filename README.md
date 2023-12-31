# Mach Eight Developer Test

### Task
​
The task is to write a function that finds pairs of integers from a list that
sum to a given value. The function will take as input the list of numbers as
well as the target sum.
​
Sample output is shown below.

```
> app 1,9,5,0,20,-4,12,16,7 12
​
+ 12,0
+ 5,7
+ 16,-4
```

**Important**: The algorithm to find the pairs must be faster than O(n^2).

### Steps to run the test:

1. Copy the code below:

```javascript
const app = (numbers, target) => {
  const arrNums = numbers.split(",");
  const arrayLen = arrNums.length;
  let loopIndex = 0;
  let loop = 0;
  let output = new Set();

  while (loop < arrayLen) {
    if (arrNums[loop] && arrNums[loopIndex]) {
      const num1 = parseInt(arrNums[loop]);
      const num2 = parseInt(arrNums[loopIndex]);
      
      const obj = {
          nums_inverted: `${num2}, ${num1}`,
          sum: num1 + num2
      }

      if (!output.has(obj.nums_inverted) && num1 > 0 && obj.sum == target) {
        output.add(`${arrNums[loop]}, ${arrNums[loopIndex]}`);
      }
    }

    // Loops and Index counters
    loopIndex = loopIndex === arrayLen - 1 ? 0 : loopIndex + 1;
    if (loopIndex === arrayLen - 1) loop++;
  }

  return Array.from(output).join(`,\n`);
};

let listNumbers = prompt("Insert the list of numbers: ");
let targetSum = prompt("The target sum: ");

if (listNumbers && targetSum) {
  console.log(app(listNumbers, targetSum));
}
```


2. Visit this [Online JavaScript Compiler](https://www.programiz.com/javascript/online-compiler/) and paste the code in the editor.
