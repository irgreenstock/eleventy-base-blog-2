---
title: Exploring Loops, Arrays and Objects Part 2
date: 2024-04-14
tags: -IG -JavaScript
---

<hr>
<div>

Looking further at using loops, arrays and objects. This time, finding different mathematical averages.

<br><h3>Mean</h3><br>

``` js
const numbers = [49, 30, 9, 245, 56, 9];

getMean = (numbers) => {
  let sum = 0
  for (let i=0; i<numbers.length; i++) {
    sum += numbers[i];
    }
    return sum/numbers.length;
}
console.log('Mean = ' + getMean(numbers));
```
<br><h3>Median</h3><br>

``` js
getMedian = (numbers) => {
  let median = 0, numsLen = numbers.length;
 numbers.sort(); 

    if (numsLen % 2 === 0) { //even
      median = (numbers[numsLen/2-1] + numbers[numsLen/2])/2;
    } else { //odd
      median = numbers[(numsLen -1)/2];
    }
  return median;
};

console.log('Median = ' + getMedian(numbers));

```
<br><h3>Mode</h3><br>

``` js
getMode = (numbers) => {
  const map = {};
  
  numbers.forEach(number => {
 
    if (!map[number]) {
      map[number] = 1;
    } else {
      map[number] += 1;
    } 
  });
  
  
 let highestValue = 0;
 let highestValueKey = -Infinity;
 
  for (let key in map) {
    const value = map[key];
    if (value > highestValue) {
      highestValue = value;
      highestValueKey = key;
    }
  }

return Number(highestValueKey);
}

console.log('Mode = ' + getMode(numbers));

 ```
<br><h3>Write a function with switch case to choose between mean, median or mode</h3><br>

 ``` js 
mmmFunction = (numbers, method) => {
  switch(method) {
    case 'getMean': 
      return `the Mean is ` + getMean(numbers)
    case 'getMedian':
      return `the Median is ` + getMedian(numbers)
    case 'getMode':
      return `the Mode is ` +getMode(numbers);
  }
}
console.log(mmmFunction(numbers,'getMedian'));

```
</div>