### freeCodeCamp -  Algorithm Challenges

### Check for Palindromes

```js
function palindrome(str) {
  // const pal = str.toLowerCase().replace(/[^a-z0-9]/g, '');
  const pal = str.toLowerCase().replace(/[\W_]/g, '');
  return pal === pal.split('').reverse().join('');
}

console.log(palindrome("eye"));
console.log(palindrome("five|\_/|four"));
console.log(palindrome("0_0(: /-\ :) 0-0"));
console.log(palindrome("A man, a plan, a canal. Panama"));
```

```js
function palindromeAdvanced(str) {
  const newStr = str.toLowerCase().replace(/[\W_]/g, '');
  const length = newStr.length - 1;
  for (let i = 0; i < (length - 1) / 2; i++) {
    if (newStr[i] !== newStr[length - i]) return false;
  }
  return true;
}

console.log(palindromeAdvanced("eye"));
console.log(palindromeAdvanced("five|\_/|four"));
console.log(palindromeAdvanced("0_0(: /-\ :) 0-0"));
console.log(palindromeAdvanced("A man, a plan, a canal. Panama"));
```

---

### Find the Longest Word in a String

- String Split
- String Length
- Math.max
- Array Reduce


```js
function findLongestWord(str) {
  let newStr = str.split(' ').map(word => word.length);
  return Math.max(...newStr);
}

console.log(findLongestWord("The quick brown fox jumped over the lazy dog"));
```


```js
function findLongestWordAdvanced(str) {
  return str.split(' ').reduce((accumulator, item) => Math.max(accumulator, item.length),0);
}

console.log(findLongestWordAdvanced("The quick brown fox jumped over the lazy dog"));
```

---

### Title Case a Sentence

Return the provided string with the first letter of each word capitalized. Make sure the rest of the word is in lower case.
For the purpose of this exercise, you should also capitalize connecting words like "the" and "of".


```js
function titleCase(str) {
  let convertToArray = str.toLowerCase().split(' ');
  let result = convertToArray.map(function (val) {
    return val.replace(val.charAt(0), val.charAt(0).toUpperCase());
  });
  return result.join(' ');
}

console.log(titleCase("I'm a little tea pot."));
```

```js
// regular expression 사용하기
function titleCaseRegex(str) {
  return str.toLowerCase().replace(/(^|\s)\S/g, (i => i.toUpperCase()));
}

console.log(titleCaseRegex("I'm a little tea pot."));
```

---

### Confirm the Ending

```js
function confirmEnding(str, target) {
  return str.substr(-target.length) === target;
}

console.log(confirmEnding("song yohan", "han"));
```

---

### Repeat a string repeat a string

```js
function repeatStringNumTimes(str, num) {
  // repeat after me
  return num > 0 ? str.repeat(num) : '';
}

console.log(repeatStringNumTimes("abc", 3));
```

---
### Truncate a String

```js
function truncateString(str, num) {
  // Clear out that junk in your trunk
  if (str.length > 3 && num > 3) {
    return str.slice(0, (num - 3)) + '...';
  } else if (str.length > num && num <= 3) {
    return str.slice(0, num) + '...';
  } 
  return str;
}

console.log(truncateString("free code camp", 3));
console.log(truncateString("A-tisket a-tasket A green and yellow basket", "A-tisket a-tasket A green and yellow basket".length + 2));
```

```js
function truncateString(str, num) {
  if (str.length > num)
    return str.slice(0, num > 3 ? num - 3 : num) + '...';  
  return str;
}

console.log(truncateString("Absolutely Longer", 2));
console.log(truncateString("A-tisket a-tasket A green and yellow basket", "A-tisket a-tasket A green and yellow basket".length + 2));
```

---


```js
function mutation(arr) {
  var origin = arr[0].toLowerCase();
  var test = arr[1].toLowerCase();
  
  for (var i = 0; i < test.length; i++) {
    if (origin.indexOf(test[i]) === -1) return false;
  }
  return true;
}

console.log(mutation(["hello", "hey"]));
console.log(mutation(["zyxwvutsrqponmlkjihgfedcba", "qrstu"]));
console.log(mutation(["Mary", "Army"]));
```

---

### Falsy Bouncer

Remove all falsy values from an array

```js
function bouncer(arr) {
  console.log(Boolean);
  return arr.filter(function(item) {
    return Boolean(item);
  });
}

function bouncer(arr) {
  return arr.filter(Boolean);
 }

console.log(bouncer([7, "ate", "", false, 9]));
console.log(bouncer([1, null, NaN, 2, undefined]));
```

---
