# Unknown Types
## Issue
Let's say you want to use `unirest` in your module, so you run something like
this:
>npm install unirest --save

Then you go into your TypeScript code and write something like this on file in
`src/`:
```ts
import * as unirest from "unirest";

export class MyClass {
    public googleIt(it:string,callback:any) {
        return unirest.get('https://www.google.com.ar/#q=' + it).end((response: any) => {
            console.log(response);
        });
    }
}
```

But when you try to transpile it, `tsc` says it doesn't know the type `unirest`
or how to use it.
So you google for a while and you find that you need to install some type
definitions, but nobody had written them and you'll probably have to write them
yourself.

## Solution
First of all, _don't panic_, create a file called `unirest.d.ts` inside `src/declarations/`
this this content:
```ts
declare module 'unirest';
```
Then go back to your class and add this at the top:
```ts
/// <reference path="./definitions/unirest.d.ts" />
import * as unirest from "unirest";

export class MyClass {
    public googleIt(it:string,callback:any) {
        return unirest.get('https://www.google.com.ar/#q=' + it).end((response: any) => {
            console.log(response);
        });
    }
}
