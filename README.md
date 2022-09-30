# Features ECMAScript-2022 (ES13)

![banner](https://plainenglish.io/assets/post-content/latest-es13-javascript-features.png)

## 1) The new method Array.prototype.at()

The at() method takes an integer value and returns the item at that index, allowing for positive and negative integers. Negative integers count back from the last item in the array.

The following "indexable" types have method .at():

-string
-Array
-All Typed Array classes: Uint8Array etc.


```javascript

const arr = [1,2,3,5,8,12];
arr[0]; // 1
arr[arr.length -1]; // 12

arr.at(0); // 1
arr.at(-1); // 12

const arr2 = [[1,2,3,], [4,5,6],[7,8,9]];
arr2[arr2.length -1][arr2[arr2.length -1].length -1];
arr2.at(-1).at(-1);

const str = 'some string';
str.at(0); // s
str.at(2); // m
```

## 2) The new property Error.prototype.cause

The cause property indicates the specific original cause of an error.
It is used when catching and re-throwing an error with a more-specific or useful error message in order to still have access to the original error.

```javascript

try{
conectToDataBase();
}catch(error){
throw new Error('Connecting to database failed.', {cause:error});
}
```

## 3) Private class features #

```javascript

class Foo {

#privateField = 42;

#privateMethod(){
return 'hello ES13';
};

static #PRIVATE_STATIC_FIELD = 22;

static #privateStaticMethod(){
return 'Hello ECMAScript 2022';
 };
}
```

## 4) Regexp Match Indices 

This upgrade will allow us to use the d character to specify that we want to get the indices (starting and ending) of the matches of our RegExp. Previously this was not possible. You could only obtain indexing data in the process of string-matching operation.

```javascript
const fruits = "Fruits: apple, banana, orange";
const regex = /(banana)/g;

const matchObj = regex.exec(fruits);

console.log(matchObj);
// [
//   'banana',
//   'banana',
//   index: 15,
//   input: 'Fruits: apple, banana, orange',
//   groups: undefined
// ]

const fruits = "Fruits: apple, banana, orange";
const regex = /(banana)/dg;

const matchObj = regex.exec(fruits);

console.log(matchObj);
// [
//   'banana',
//   'banana',
//   index: 15,
//   indices:[
//      [15, 21],
//      [15, 21]
//   ]
//   input: 'Fruits: apple, banana, orange',
//   groups: undefined
// ]
```
## 5) Await operator at the top-level

```javascript
// Loading modules dynamically
const strings = await import(`./example.mjs`);

// Using a fallback if module loading fails
let jQuery;
try {
  jQuery = await import("https://cdn-a.com/jQuery");
} catch {
  jQuery = await import("https://cdn-b.com/jQuery");
}

// Using whichever resource loads fastest
const resource = await Promise.any([
  fetch("http://example1.com"),
  fetch("http://example2.com"),
]);
 ```
