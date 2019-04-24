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
A declarative programming paradigm which treats computation as the evaluation of mathematical functions, and avoids changing state and mutating data.

---

## Programming paradigms
Refers to the style of structuring a program, eg.
- Object-oriented programming: Everything modeled as an object
- Event-driven pogramming: Flow determined by events
- Imperative programming: Focused on how a program should operate

---

## Declarative programming
A style of programming by declaring your intentions without specifying how it should be done

...

### Comparison with imperative programming

Declarative - I want to get the first names of all users with less than 5 posts

vs

Imperative - For each user in the list of users, if the user has less than 5 posts, add the first name of that user to the result

---

## Mathematical function
A function describes how a quantity varies with respect to another quantity

...

y is a function of x, which varies by x + 1
```
y = f(x) = x + 1
```


---

```js
users
  .filter(user => user.posts < 5)
  .map(user => user.firstName)
```

...

