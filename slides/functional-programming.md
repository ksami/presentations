---
title: Functional Programming
separator: \n---\n
verticalSeparator: \n...\n
theme: solarized
revealOptions:
    transition: 'slide'
---

# Functional Programming

---

## What?
A declarative programming paradigm which treats computation as the evaluation of mathematical functions, and avoids changing state and mutating data

---

## Why?
- Easier to test
- Easier to reason about
- Easier to write multi-threaded applications

---

## Programming paradigms
- Refers to the style of structuring a program, eg.
  - Object-oriented programming: Everything modeled as an object
  - Event-driven pogramming: Flow determined by events
  - Imperative programming: Focused on how a program should operate

---

## Functional Programming Concepts
- Function
- Function composition
- Pure function
- Higher order function
- No shared state
- No side effects
- Immutability
- Declarative

...

### Function
- In the mathematical sense, a mapping from one set (eg. numbers) to another
  - If `f = x => x - 1`, then `f(1)` maps to `0`

...

### Function composition
- The output of one function is the input for the next function
  - `f(g(x))` means `let i = g(x); f(i);`

...

### Pure function
- Given the same input, always returns the same output
  - `f(1)` will always return `0` no matter how many times it is called
  - Pure functions with composition, `f(g(x)) === g(f(x))`

...

### Higher order function
- Takes and/or returns other functions as inputs/outputs
  - ```js
    // apply is a function which takes function f as input,
    // returns a function which takes x as input
    // and returns the result of f applied to x

    const apply = f => x => f(x);
    const minusOne = apply(y => y - 1);

    minusOne(1) === 0;           // true
    apply(z => z + 2)(1) === 3;  // true
    ```

...

### No shared state
- State shared across more than one scope
- Causes result to be affected by order of execution
  - ```js
    let player = { score: 4 };
    const hasWon = () => player.score >= 5;
    const updateScore = () => player.score++;

    updateScore();
    hasWon();
    // player has won

    player = { score: 4 };
    hasWon();
    updateScore();
    // player has not won
    ```

...

### No side effects
- External state changes other than return value
  - ```js
    function minusOne(x) {
      // nothing suspicious here
      deleteAllDatabases();
      return x - 1;
    }
    ```

...

### Immutability
- Data should not be changed
  - If `x = 0` then `x` should never be `1` or `'hello'` or `[]`

...

### Declarative
- Specifying what should be done, opposed to imperative - how something should be done
- Intent of the code is clear

...

Quiz: In 10 seconds, what does this function do?

...

#### Quiz
    function someFunction(players) {
      const results = [];
      for (let i = 0; i <= players.length; i++) {
        if (players[i].score >= 5) {
          results.push(player[i].name);
        }
      }
      return results;
    }

...

...

There was a bug in the previous code though...

Let's try another one

...

#### Quiz
    function anotherFunction(players) {
      return players
        .filter(player => player.score >= 5)
        .map(player => player.name);
    }

...

And another

...

#### Quiz
    SELECT name FROM players WHERE score >= 5


---

## Summary
- Functions should not affect the outside world
- Declarative code makes intent clear

---

## References
- https://medium.com/javascript-scene/master-the-javascript-interview-what-is-functional-programming-7f218c68b3a0
- http://blog.jenkster.com/2015/12/what-is-functional-programming.html
- https://www.keycdn.com/blog/functional-programming

---

# Fin
