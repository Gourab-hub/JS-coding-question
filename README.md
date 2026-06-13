# JS-Modern ES6+-Interview-questions-

1. JS Modern ES6+ string to char count

```javascript
const str = "programming";

const charCountMap = str.split("").reduce((acc, char) => {
    // If the character doesn't exist in the object, initialize it to 0, then add 1
    acc[char] = (acc[char] || 0) + 1;
    return acc;
}, {});

console.log(charCountMap);
```

{
  "p": 1,
  "r": 2,
  "o": 1,
  "g": 2,
  "a": 1,
  "m": 2,
  "i": 1,
  "n": 1
}


2. First non-repeating character using JS

```javascript
function firstNonRepeating(s) {
    // 1. Build an insertion-ordered frequency map (LinkedHashMap equivalent)
    const map = s.split("").reduce((acc, char) => {
        acc.set(char, (acc.get(char) || 0) + 1);
        return acc;
    }, new Map());

    // 2. Iterate to find the first key with a count of 1
    for (let [key, value] of map.entries()) {
        if (value === 1) {
            return key;
        }
    }
    
    return null;
}

// Function Call
console.log(firstNonRepeating("programming")); 
/* OUTPUT:
'p'
*/

3. count character frequency from a string using JS


```javascript
const name = "Gourab Banik";

const charCountMap = name
    .split(" ")                            // Split by space -> ["Gourab", "Banik"]
    .map(word => word.toLowerCase())       // Lowercase each word -> ["gourab", "banik"]
    .flatMap(word => word.split(""))       // Flatten to characters -> ['g', 'o', 'u', 'r', 'a', 'b', 'b', 'a', 'n', 'i', 'k']
    .reduce((acc, c) => {                  // GroupingBy and counting equivalent
        acc[c] = (acc[c] || 0) + 1;
        return acc;
    }, {});

console.log(charCountMap);
```
OUTPUT:
{
  g: 1,
  o: 1,
  u: 1,
  r: 1,
  a: 2,
  b: 2,
  n: 1,
  i: 1,
  k: 1
}


4. Sort distinct number using JS
```javascript
const arr = [5, 3, 1, 2, 3, 5, 4, 2];

// 1. Remove duplicates using a Set, then spread into a new array
// 2. Sort numerically using a comparator function
const result = [...new Set(arr)].sort((a, b) => a - b);

console.log("Sorted Distinct Numbers:");
console.log(result);
/* OUTPUT:
Sorted Distinct Numbers:
[ 1, 2, 3, 4, 5 ]
*/
```
