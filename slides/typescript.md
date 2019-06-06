---
title: Typescript
separator: \n---\n
verticalSeparator: \n...\n
theme: sky
revealOptions:
    transition: 'fade'
---

# Typescript

---

## What?
Typescript is a superset of Javascript which adds optional typing

---

## History
- Typescript created by Microsoft
- Microsoft Technical Fellow Anders Hejlsberg, lead architect of C#, core developer of Typescript
- Microsoft Bing, Office 365, Windows 8 apps teams working with Javascript
- Encountered difficulties scaling Javascript apps

---

## Features

---

### Static type analysis
- Type annotations added to normal Javascript
  - Program analysis and tooling eg. Intellisense
- Type inference to decrease amount of explicit typing
- Compile time error checking
  - `--strictNullChecks` compiler option to check for `null` and `undefined`
- Type definitions for 3rd-party dependencies available from NPM eg. for `lodash`, from `@types/lodash`

...

### Compatibility with Javascript
- Plain Javascript code is also valid Typescript code
  - Allows for gradual introduction of Typescript into an existing Javascript codebase

...

### Compiles to Javascript
- Can code using latest version and compile to older versions for compatibility eg. Code using ES2017 features, output ES5 code
- Can specify module system for output eg. Code using ES2015 `import`/`export`, output commonjs `require` for Node.js

---

## Disadvantages

...

### Compile step
- Code -> Run becomes Code -> Compile -> Run
- Compile step delays workflow cycle
- Modern frontend development already has some sort of buildchain, compile step easily added in
- Node.js development seldom has buildchain
- Impact lessened with Typescript compiler `--watch` option to automatically re-compile when files are changed

...

### Type definitions
- `.d.ts` type definition files have to be manually written for any 3rd-party dependencies with no definitions
- `.d.ts` type definition files may be too specific or not specific enough
- Tendency to over-specify types eg. for Data Transfer Objects (DTO)
- Typescript's type system difficult to apply to certain Javascript patterns eg. ES2015 Proxy
- Time and effort required to fix typing issues
- Typescript team has been improving the type system

...

### Testing and debugging
- Source maps required for debuggers to track exact line in Typescript source
- Latest VSCode updates provide greater and simpler integration with Typescript

---

# Fin
