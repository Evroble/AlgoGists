# Validate Subsequence

##Prompt:

Given two non-empty arrays of integers, write a function that determines whether the second array is a subsequence of the first one.

A subsequence of an array is a set of numbers that aren’t necessarily adjacent in the array but that are in the same order as they appear in the array. For instance, the numbers [1, 3, 4] form a subsequence of the array [1, 2, 3, 4], and so do [2, 4]. Note that a single number in an array and the array itself are both valid subsequences of the array.

Example:

```
Array = [5, 9, 6, 8, -1, 7, 2]
Subsequence = [6, -1, 7]
Expected Output: true
```

###Solution 1:
```js
function isValidSubsequence(array, sequence) {
  let arrIdx = 0;
  let seqIdx = 0;

  while (arrIdx < array.length && seqIdx < sequence.length) {
    if (array[arrIdx] === sequence[seqIdx]) {
      seqIdx++;
      arrIdx++;
    }
  }
  return seqIdx === sequence.length;
}
```
Time Complexity: O(n)
Space Complexity: O(1)

###Solution 2:
```js
function isValidSubsequence(array, sequence){
  let seqIdx = 0;
  for (const value of array) {
      if(seqIdx === sequence.length) break;
      if(sequence[seqIdx] === value) seqIdx++;
  }
return seqIdx === sequence.length;
}
```
Time complexity: O(n)
Space complexity: O(1)

