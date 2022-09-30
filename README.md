# features ECMAScript-2022 (ES13)

![banner](https://plainenglish.io/assets/post-content/latest-es13-javascript-features.png)

## 1) The new method Array.prototype.at()

The at() method takes an integer value and returns the item at that index, allowing for positive and negative integers. Negative integers count back from the last item in the array.


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
 
