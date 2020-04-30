# Bearer Authorization

## bearer authentication

- following `signin` with either basic or OAuth systems knows if valid or not
- rather than constant validation, a token can be created to act as a shorthand for user/pass
- a token has enough info inside to look up a user and confirm access before continuing the work
- every subsequent request must be authenticated with that token
- the token contains the needed info when decoded each time
- tokens can be signed with secrets or public/private keys

## when to use JWT

- authorization > once logged in, each subsequent request will include the jwt
  - this is common with single-sign-on
Information Exchange > sender and reader both need the matching key

## Additional Resources

### video

- [JWTs explained](https://www.youtube.com/watch?v=926mknSW9Lo)

### Skim

- [intro to JWT](https://jwt.io/introduction/)
- [are JWTs Secure?](https://stackoverflow.com/questions/27301557/if-you-can-decode-jwt-how-are-they-secure)

### more

- [npm jsonwebtoken docs](https://www.npmjs.com/package/jsonwebtoken)