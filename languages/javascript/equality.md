`==` vs `===`
The **strict equality operator**, `===` behaves the same as **abstract equality operator**, `==` except no type conversion is done, the types must be same to be considered equal.

Interesting cases when `==` attempts to convert types before comparing for equality:
```js
'' == '0'           // false
0 == ''             // true
0 == '0'            // true

false == 'false'    // false
false == '0'        // true

false == undefined  // false
false == null       // false
null == undefined   // true

' \t\r\n ' == 0     // true
```

Source: https://stackoverflow.com/questions/359494/which-equals-operator-vs-should-be-used-in-javascript-comparisons
