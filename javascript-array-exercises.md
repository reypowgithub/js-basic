
# JavaScript Basic Array Exercises (Without Looping)

Practice working with arrays in JavaScript without using loops.

---

## 1. Create an Array

Create an array called `fruits` that contains:

- "Apple"
- "Banana"
- "Orange"

```javascript
const fruits = ["Apple", "Banana", "Orange"]
console.log(fruits)
```

---

## 2. Access Array Elements

Print the first and the last element of the `fruits` array.

```javascript
// your code here
let firstFruit = fruits[0]
let lastFruit = fruits[fruits.length - 1]
console.log(firstFruit)
console.log(lastFruit)
```

---

## 3. Add Element to Array

Add `"Mango"` to the end of `fruits`.

```javascript
fruits.push("Mango")
console.log(fruits)
```

---

## 4. Add Element to Beginning

Add `"Grape"` to the beginning of `fruits`.

```javascript
fruits.unshift("Grapes")
console.log(fruits)
```

---

## 5. Remove Last Element

Remove the last element from `fruits`.

```javascript
fruits.pop()
console.log(fruits)
```

---

## 6. Remove First Element

Remove the first element from `fruits`.

```javascript
fruits.shift()
console.log(fruits)
```

---

## 7. Check Array Length

Print how many items are in the `fruits` array.

```javascript
fruits.length
console.log(fruits.length)
```

---

## 8. Check if Value Exists

Check if `"Banana"` exists in the `fruits` array.

Expected output → `true` or `false`

```javascript
fruits.includes("Banana")
console.log(fruits.includes("Banana"))
```

---

## 9. Find Element Index

Find the index of `"Orange"` in the `fruits` array.

```javascript
console.log(fruits.indexOf("Orange"))
```

---

## 10. Convert Array to String

Convert the `fruits` array to a single string separated by commas.

Example output → `"Apple,Banana,Orange"`

```javascript
console.log(fruits.toString())
```

---

Happy Coding! 🚀
