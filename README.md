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
