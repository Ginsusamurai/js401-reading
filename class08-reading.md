# Reading 08 - Express Routing & Connected API

- routes can be handled in modules, what's the impact?

  - server now has a VERY truncated use, shows the possible route groupings and middleware services
  - data models and routes are kept in their own segregated areas
  - index is just a landing 'page', no other use


## addtional resources

### articles

- [using express routing](https://expressjs.com/en/guide/routing.html)
  - `app.all` handles all methods for a provided route
  - path-to-regex is used on routing so you can have multiple matches available, not just litteral
  - Route Parameters (alphaNumeric ONLY)
    ```javascript
    Route path: /users/:userId/books/:bookId
    Request URL: http://localhost:3000/users/34/books/8989
    req.params: { "userId": "34", "bookId": "8989" }
    ```
  

- [express routing](https://scotch.io/tutorials/learn-to-use-the-new-router-in-expressjs-4)
  - `router` is in express 4.0, acts as a smaller express app
  - let's you make custom sub-routes and modularize them
  - used like middleware `app.use('/foo', router)`