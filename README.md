# features ECMAScript-2022 (ES13)

```javascript

const arr = [1,2,3,5,8,12]

arr[0] // 1

arr[arr.length -1] // 12

arr.at(0) // 1

arr.at(-1) // 12

const arr2 = [[1,2,3,], [4,5,6],[7,8,9]]

arr2[arr2.length -1][arr2[arr2.length -1].length -1]

arr2.at(-1).at(-1)

const str = 'some string'
str.at(0) // s
str.at(2) // m
```

```javascript

try{
conectToDataBase()
}catch(error){
throw new Error('Connecting to database failed.', {cause:error})
}
```
