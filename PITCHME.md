# Modern TypeScript

As of 2019-07-24

Note:

- View this presentation at https://gitpitch.com/mattyclarkson/slides-typescript

---

### Me

- Built [EF Hello](https://www.efhello.com/) with TypeScript
- Built various web sites with TypeScript
- Background in native languages (so like types 🙂)

---

### What is TypeScript?

- A typing layer on top of JavaScript

```
interface IController {
  execute(ctx: IContext): Promise<IResult>;
  readonly count: number;
  name?: string;
}
```

Note:

- View [project](https://www.typescriptlang.org/)
- A transpiler converts source code into more source code
- Interface has:
  - Async function interface
  - A readonly property
  - An optional property
- Scales _really_ well
- Prevents lots of errors that occur by type conversion

---

### What is `tsc`?

- The TypeScript transpiler
- Does the type checking
- Can generate valid JavaScript

Note:

- Can handle all project compilation
- However, better to use Babel due to ecosystem support

---

### What is Babel?

- A transpiler for JavaScript
- Modern JavaScript into backwards compatible
- Automatically inserts polyfills
- Allows use of new language features

Note:

- Read about [Babel](https://babeljs.io)
- A polyfill is JavaScript code that implements a new modern feature in
- backwards compatible JavaScript
- Has huge ecosystem support
- Can do in memory streamed transpilation
- Follows the TC39 staged proposals

---

### TC-39 Proposal Process

- Stage proposal process with four stages
- Strawperson → Proposal → Draft → Candidate → Finished
- Finished proposals rolled into yearly release
- Babel can load staged proposals

Note:

- View the [process](https://tc39.es/process-document/)

---

### TypeScript support in Babel

- Babel supports the TypeScript syntax
- Install `@babel/preset-typescript`
- Does not perform type checking
- Still need `tsc --noEmit`

Note:

- Need [`@babel/preset-typescript`](https://babeljs.io/docs/en/babel-preset-typescript)
- Prevents mutliple polyfills of `tsc`/`Babel` both transpiling
- Fits nicely into JavaScript ecosystem
- Makes type checking a linting step
- Can watch for changes, speeding up development
