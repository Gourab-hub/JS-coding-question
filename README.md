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
