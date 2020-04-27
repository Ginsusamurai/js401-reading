# Authentication - class 11 reading

## user modeling

- names and emails can be in plain text but passwords need encryption
- to share info across users, use a `second profile model` that holds data and strictly limits acces to the profile model

## cryptography

- science of encoding messages

## hash algorithms

- takes a piece of data and produces a hash that is difficult to decode
- to login, user sends the same password with the server can encode with same has algorithm
- server compares the arriving hash against the stored hash

## Cypher Algorithms

- cryptographic cypher algorithm takes data, a key, and makes encrypted data.
- tokens can be made similarly and passed back and forth 
- server decyrpting the token can find the seed and therefore the user

## Basic Authorization

- username and password are joined, then `base 64` encoded, then appended to `basic`. This is the auth header
- `atob` and `btoa` to conver to/from base64 encoding

### articles

- [securing passwords](http://dustwell.com/how-to-handle-passwords-bcrypt.html)
- [basic auth](https://en.wikipedia.org/wiki/Basic_access_authentication)
- [intro to jwt](https://jwt.io/introduction/)
- [OWASP auth cheatsheet](https://www.owasp.org/index.php/Authentication_Cheat_Sheet)
- [bcrypt docs](https://www.npmjs.com/package/bcrypt)