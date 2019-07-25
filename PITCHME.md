# Modern TypeScript

As of 2019-07-24

Note:

- View this [presentation][presentation]

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

- View [project][typescript]
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

- Read about [Babel][babel]
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

- View the [process][tc-39-process]

---

### TypeScript support in Babel

- Babel supports the TypeScript syntax
- Install `@babel/preset-typescript`
- Does not perform type checking
- Still need `tsc --noEmit`

Note:

- Need [`@babel/preset-typescript`][babel-preset-typescript]
- Prevents mutliple polyfills of `tsc`/`Babel` both transpiling
- Fits nicely into JavaScript ecosystem
- Makes type checking a linting step
- Can watch for changes, speeding up development

---

### Workflow

- Bundle with [`rollup`][rollup]
  - Transpiles with Babel
- Type check with `tsc`
- [Prettier][prettier] for formatting
- Lint with [ESLint][eslint]
- Docs with [TypeDoc][typedoc]
- Test with [Jest][jest]
- Release with [`semantic-release`][semantic-release]
- Commit hooks with [Husky][husky]

Note:

- Code is written in `lib/` in TypeScript`
- Rollup uses Babel to transpile
  - Creates ECMAscript module
  - Create UMD for node
- `tsc`
  - Creates type definitions
  - Does type checking
- Prettier does (all languages) formatting
- Linting can help catch errors early
  - Turn on ESLint checks
- Documentation of API is useful
  - TypeDoc isn't great but good enough
- Jest is testing framework from Facebook
  - Useful headless testing
  - Has different testing environments
  - headless browser testing with https://webdriver.io
- Semantic release automates continuous delivery
  - Bumps version
  - Generates changelog
  - Creates tag
  - Publishes package on `npm`
  - Has plugins to automate any continuous delivery
- Commit hooks help maintain code quality
  - Setup conventional commits to conform to semantic release
  - Check code format on commit
  - Test code on push

[webdriver]: https://webdriver.io
[prettier]: https://prettier.io/
[rollup]: https://rollupjs.org
[presentation]: https://gitpitch.com/mattyclarkson/slides-typescript
[typescript]: https://www.typescriptlang.org/
[tc-39-process]: https://tc39.es/process-document/
[babel]: https://babeljs.io
[babel-preset-typescript]: https://babeljs.io/docs/en/babel-preset-typescript
[eslint]: https://eslint.org/
[typedoc]: https://typedoc.org/
[jsdoc]: https://jsdoc.app/
[jest]: https://jestjs.io/
[husky]: https://github.com/typicode/husky
[semantic-release]: https://semantic-release.gitbook.io/semantic-release/
