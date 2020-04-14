# Readings: Classes, Inheritance, Functional Programming

## Functional Programming

* Functional programming is the distinction between pure code (no side effects) and impure code
  * procedural is a sequence of steps
  * object oriented is solution as communicating objects
  * functional is modeling as pure functions
* `Pure Functions` give a value based on ONLY what it was passed
  * outside variables are an example of impure functions
* `high order` functions are passed other functions or return a function
  * higher order functions are things like `map, filter, reduce`

## Objects and Inheritance

* JS has prototype-based inheritance rather than Class Based inheritance
* for classes...
  `function()` becomes `class{}`
  `call()` becomes `extends`

## Errors

* good error messages make debugging much easier
  1. timestamp
  1. message about the problem
  1. cause of problem
  1. consistent format
  1. severity level (low-high, 0-10)
* JS can throw an error on command which lets them be `caught` rather than breaking the whole app
* extensive lists of System Errors can help debug 
  - EACCESS - an attempt to access a file without the right permissions
  - EADDRINUSE - an attempt to start a server on a PORT that is already in use
  - ECONNREFUSED - a connection was deliberately refused by the target machine
  - ECONNRESET - a connection was forcibly closed by a peer
  - EEXIST - a file exists and the attempted action required that it didn’t
  - EISDIR - an action expected to act on a file but found a directory
  - EMFILE - too many files were open for your operating system to handle
  - ENOENT - an action expected a file, but did not find one
  - ENOTDIR - an action expected a directory, but found something else
  - ENOTEMPTY - an action expected an empty directory, but found one with data in it
  - EPERM - an attempt to do something that you currently don’t have permissions to do
  - EPIPE - an attempt to write data to a connection that had been closed

Addtional Materials
[context](https://www.youtube.com/watch?v=fjJoX9F_F5g)

* what `this` is at a given time
* default is the `window` object
  * inside of an object `this` is the object itslef (such as in a function)
* ways to set context `call, apply, bind`
  * can change the context of a specific function on the go
  * call takes the args (context, n,n+1)
  * apply takes the args (context, [])
  * bind forces a context if you save a variant function with the bind
* using this you can save the current `this` to a variable and then pass that later on



[Inheritance and the prototype chain](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain)

[this](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this)

[classes](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes)

[node error docs](https://nodejs.org/dist/latest-v6.x/docs/api/errors.html)