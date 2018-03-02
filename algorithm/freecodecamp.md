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