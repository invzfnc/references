### Export

```js
// export an array
export let nums = [1, 2, 3, 4, 5];
// export a constant
export const PI = 3.142;
// export a class
export class User {
    constructor(name) {
        this.name = name;
    }
}
```

or

```js
// say.js
function sayHi() {
    alert("Hi");
}
function sayBye() {
    alert("Bye");
}
export {sayHi, sayBye};
```

### Import

```js
// main.js
import {sayHi, sayBye} from "./say.js";
// alias
// import {sayHi as hi, sayBye as bye} from "./say.js";
// aliasing is also possible for exports: `export {x as y}`
sayHi();
sayBye();
```

or

```js
// main.js
import * as say from "./say.js";

say.sayHi();
say.sayBye();
```

### `export default`
For modules that only declare a single entity, e.g. a module `user.js` that only exports a single class `User`. There may be only one `export default` per file. Import can be done without curly braces.

```js
// user.js
export default class User {
    constructor(name) {
        this.name = name;
    }
}

// main.js
import User from './user.js';  // not {User}, just User
new User("John");
```
