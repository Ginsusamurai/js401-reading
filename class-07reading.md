# Reading 07 - Express

## routing

- event driven
  - `app.get('/foo', (req,res) => {})`
  - vanialla JS and jquery style
- REQ object
  - app.get('/api/:foo') = `/:parameters` on the `req.params` property
  - http://server/route?foo=bar = `req.query`
- RES object
  - `send()` and `status()`
  - sends headers
    - cookies
    - status codes

## express middleware

- functions that a `req` goes through
- contain req, res, next params
- `application` and `route` mw
- `app` mw
  - error handling
  - use other routes
  - apply defaults
  - json, body, form parsing
  - run on all `req`s
- Route MW
  - for specific routes
  - usually for `logged in?`, `ip query` and `are you new?`
- how to use...
  - logging
  - dynamic model loading
  - browser, location, user data
  - consistent data transition, modeling, preperation (pre-render)

## Modularization and separation of concerns

- modularize code in to logical chunks
- each thing should be the best at what it does (single use)
- `move files around until it feels right`

## CRUD operations with REST and Express

- create `post`
- read `get`
- update `put`
- destroy `delete`

## server testing

- avoid starting the server to test
- expor the server as a module in a lib
- run `supertest` to run tests
  - this doesn't run the server and thus removes a break point
- can wrap superagent in a module
  - this allows for mock data
  - `__mocks__` folder with `agent.js`
  - `jest.mock()` will be used by jest now

## test pyramid

- unit: server internal functions
  - mock any integrations
- integration: service connections
  - connect to other services
- acceptance
  - server may be a dependency of other tests

## addtional resources

### videos
- [express middleware explained](https://www.youtube.com/watch?v=9HOem0amlyg)

### articles
- [using express middleware](https://expressjs.com/en/guide/using-middleware.html)
- [express middleware](https://www.tutorialspoint.com/expressjs/expressjs_middleware.htm)
- [using express routing](https://expressjs.com/en/guide/routing.html)
- [supertest](https://github.com/visionmedia/supertest)
- [express middleware list](https://expressjs.com/en/resources/middleware.html)
- [http status codes](https://www.restapitutorial.com/httpstatuscodes.html)