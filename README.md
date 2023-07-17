# Mach Eight Developer Test

### Steps:

1. Copy the code below:

```javascript
const app = (numbers, target) => {
  const arrNums = numbers.split(",");
  const loops = arrNums.length * arrNums.length;
  let loopIndex = 0;
  let loop = 0;
  let output = "";

  for (let index = 0; index < loops; index++) {
    if (arrNums[loop] && arrNums[loopIndex]) {
      const num1 = parseInt(arrNums[loop]);
      const num2 = parseInt(arrNums[loopIndex]);
      const numsInverted = `${arrNums[loopIndex]}, ${arrNums[loop]}`;
      const sum = num1 + num2;

      if (output.indexOf(numsInverted) === -1 && num1 > 0 && sum == target) {
        output += `${arrNums[loop]}, ${arrNums[loopIndex]}\n`;
      }
    }

    // Loops and Index counters
    loopIndex = loopIndex === arrNums.length - 1 ? 0 : loopIndex + 1;
    if (loopIndex === arrNums.length - 1) loop++;
  }

  return output;
};

let listNumbers = prompt("Insert the list of numbers: ");
let targetSum = prompt("The target sum: ");

if (listNumbers && targetSum) {
  console.log(app(listNumbers, targetSum));
}
```


2. Visit this [Online JavaScript Compiler](https://www.programiz.com/javascript/online-compiler/) and paste the code in the editor.

That's all!
