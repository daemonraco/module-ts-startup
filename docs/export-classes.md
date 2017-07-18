# Exporting Classes
## What's this about?
You'll probably know this one, but in any case, let's talk about it.

Let's say you've built a class called `MyAwesomeClass` in a typescript file at
`src/my-awesome-class.ts` and you want that whoever imports your module be able to
use it.

## Solution
A way to solve this is to write something like this in your `index.ts` file:
```ts
import { MyAwesomeClass } from './my-awesome-class';

export = {
    MyAwesomeClass: MyAwesomeClass
};
```

## How to use it
Let's say you're writing a code where your module is installed and you want to
create an instance of your class, if that's the case, this code can give you and
idea of how to use it:
```ts
var myModule = require('my-module');
var instance = new myModule.MyAwesomeClass();
```
