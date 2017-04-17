# ES6 Syntax Basics

An overview of essential syntax in JavaScript (ES6+).

## Arrow Functions

Arrow functions provide a concise syntax to express functions. This is nice because most of what we do in JavaScript is write functions, so a clear, concise way to express functions is very convenient.

Arrow functions have the following advantages:

1. They're expressed using an arrow, `=>` instead of the `function` keyword.
2. If your function body simply returns the result of a single expression, you may use an implicit return. Simply omit the function body braces (`{}`), and the `return` keyword. E.g., `const isTrue = (value) => value === true;` is equivalent to `const isTrue = value => { return value === true; };`
3. If your function takes only one parameter, and your function signature does not use an operator such as the rest operator (`...`), or the default value operator (`=`), you can omit the parenthesis, e.g., `const isTrue = (value) => value === true;` is equivalent to `const isTrue = value => value === true;`

### Exercise:

Write an arrow function that returns `true` if a number is even, `false` otherwise. It should have the following signature:

```js
isEven(n) => Boolean
```

Hint: A number is even if it is evenly divisible by `2`, meaning that the remainder after dividing will be `0`. The **modulo operator** can be used to find the remainder of a division. e.g., `4 % 2 === 0`, so `4` is *even.* `5 % 2 === 1`, so `5` is *odd.*



Arrow functions do not behave the same way as functions declared with the `function` keyword. They have the following differences:

1. Arrow functions don't have an `arguments` object. ES6 provides the the rest operator (`...`), which gathers zero or more arguments together into an array. This is considered to be a better alternative to the `arguments` object, which was commonly used to access arguments prior to ES6. Since the arguments object doesn't have the capabilities of a real array, most users copy its contents to a real array before attempting to use them. Because of the rest operator, this is no longer necessary in ES6.
2. Arrow functions don't have their own `this` context. In method calls, `this` is a special variable used to operate on an object to which the method is bound. In arrow functions, `this` always refers to the object bound to `this` in the lexical scope. Since arrow functions don't have their own slot for a `this` binding, you also can't rebind `this` to an arrow function using the `Function.prototype.bind()` method.
3. Arrow functions can't be used as constructor functions. If you try to call use an arrow function with the `new` keyword, it will throw an error. For example, if you try to use `new` with an arrow function called `Foo`, V8 will throw the following: `TypeError: Foo is not a constructor`.
4. Because you can't use arrow functions as constructors, arrow functions will never have their own bindings for `super()` or `new.target`, which are only useful in the context of constructor functions.


