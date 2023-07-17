# Mach Eight Developer Test

### Steps:

1. Copy the code below:

```javascript
const app = (numbers, target) => {
  let output = "";
  const arrNums = numbers.split(",");

  arrNums.forEach((num1) => {
    arrNums.forEach((num2) => {
      if (num1 !== num2) {
        const sum = parseInt(num1) + parseInt(num2);
        const nums = `${num2}, ${num1}`;
        if (output.indexOf(nums) === -1 && num1 > 0 && sum == target) {
          output += `${num1}, ${num2}\n`;
        }
      }
    });
  });

  return output;
};

let listNumbers = prompt('Insert the list of numbers: ');
let targetSum = prompt('The target sum: ');

if (listNumbers && targetSum) {
  const pairs = app(listNumbers, targetSum);
  alert(pairs);
}
```


2. Visit this [Online JavaScript Compiler](https://www.programiz.com/javascript/online-compiler/) and paste the code in the editor.

That's all!
