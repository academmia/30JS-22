
# Create an array

```js

// 'fruits' array created using array literal notation.
// ...

// 'fruits2' array created using the Array() constructor.
// ...

// 'fruits3' array created using String.prototype.split().
// ...

```
---
# Create a string from an array

```js

const fruits = ['Apple', 'Banana'];
// ...

```

---

# Access an array item by its index

```js

const fruits = ['Apple', 'Banana'];

// The index of an array's first element is always 0.
// ...

// The index of an array's second element is always 1.
// ...

// The index of an array's last element is always one
// ...

// Using a index number larger than the array's length
// ...

```

---

# Find the index of an item in an array

```js

const fruits = ['Apple', 'Banana'];
// ...

```

---
# Check if an array contains a certain item

```js

const fruits = ['Apple', 'Banana'];
// ...

```

---

# Append an item to an array

```js

const fruits = ['Apple', 'Banana'];
// ...
// 3

```

---

# Remove the last item from an array

```js

const fruits = ['Apple', 'Banana', 'Orange'];
// ...

```

---

# Remove multiple items from the end of an array

```js

const fruits = ['Apple', 'Banana', 'Strawberry', 'Mango', 'Cherry'];
// ...
```

---

# Truncate an array down to just its first N items

```js

const fruits = ['Apple', 'Banana', 'Strawberry', 'Mango', 'Cherry'];
// ...

```

---

# Remove the first item from an array

```js

const fruits = ['Apple', 'Banana'];
// ...

```

---

# Remove multiple items from the beginning of an array

```js

const fruits = ['Apple', 'Strawberry', 'Cherry', 'Banana', 'Mango'];
// ...

```

---

# Add a new first item to an array

```js

const fruits = ['Banana', 'Mango'];
// ...

```

---

# Remove a single item by index

```js

const fruits = ['Strawberry', 'Banana', 'Mango'];
// ...

```

---

# Remove multiple items by index

```js

const fruits = ['Apple', 'Banana', 'Strawberry', 'Mango'];
// ...

```

---

# Replace multiple items in an array

```js

const fruits = ['Apple', 'Banana', 'Strawberry'];
// ...

```

---

# Iterate over an array

```js

const fruits = ['Apple', 'Mango', 'Cherry'];
// ...

```

---

# Call a function on each element in an array

```js

const fruits = ['Apple', 'Mango', 'Cherry'];
// ...

```

---

# Merge multiple arrays together

```js

const fruits = ['Apple', 'Banana', 'Strawberry'];
const moreFruits = ['Mango', 'Cherry'];
// ...

```

---

# Copy an array

```js

const fruits = ['Strawberry', 'Mango'];

// Create a copy using spread syntax.
// ...

// Create a copy using the from() method.
// ...

// Create a copy using the slice() method.
// ...

```

- these are shallow copies

> If you instead want a deep copy of an array, you can use JSON.stringify() to convert the array to a JSON string, and then JSON.parse() to convert the string back into a new array that's completely independent from the original array.

`const fruitsDeepCopy = JSON.parse(JSON.stringify(fruits));`

---

# Grouping the elements of an array

```js

const inventory = [
  { name: 'asparagus', type: 'vegetables' },
  { name: 'bananas', type: 'fruit' },
  { name: 'goat', type: 'meat' },
  { name: 'cherries', type: 'fruit' },
  { name: 'fish', type: 'meat' },
];

// ...

```

---

# Converting between strings and arrays

```js

const data = 'Manchester,London,Liverpool,Birmingham,Leeds,Carlisle';
// ...

// using toString()
const dogNames = ['Rocket','Flash','Bella','Slugger'];
// ...

```

- toString() is arguably simpler than join() as it doesn't take a parameter, but more limiting. With join() you can specify different separators, whereas toString() always uses a comma.