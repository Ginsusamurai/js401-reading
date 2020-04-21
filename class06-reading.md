# HTTP and REST

## HTPP

- Hyper Text Transfer Protocol is stateless
- defines how req/res should be formatted

## HTTP Requests

- `Method`, `URL`, `HTTP Version` and `Headers` with an optional `Body`
- `Safe` methods should be used for info retrieval and not change server state
- `Idempotent` should get same response for 2 identical requests
- `Cahceable` client can cache the responsed

## HTTP Response

- formatted text transfered with TCP
- `HTTP Version`, `Status Code` and `Status Message`

## REST

- `RE`presentational `S`tate `T`ransfer
- uses common `Methods` (verbs) to operate on state of resource (noun)
- RESTful endpoint is a URI identifies the resource
  - RESTful Endpoint: http://api.server.com/api/v1/people

  - `http://` - Protocol/Scheme
  - `api.server.com` - Domain or Server
  - `/api/v1` - API Endpoint
  - `/people` - The resource (This identifies a collection: all people)
  - `/people/12345` - A more specific resource: The person with id 12345

## REST Documnetation (Swagger)

- Docs are made with `Open API`, formerly known as Swagger


## Additional Resources

### Videos

- [http and rest](https://www.youtube.com/watch?v=Q-BpqyOT3a8)

### Bookmark / Skim

- [http basics](https://code.tutsplus.com/tutorials/http-the-protocol-every-web-developer-must-know-part-1--net-31177)
- [what is ReST](https://restfulapi.net/)
- [swagger documentation](https://swagger.io/docs/)
- [swagger editor](https://editor.swagger.io/)
- [http reference](https://code-maze.com/the-http-reference/)
- [rest reference](https://www.restapitutorial.com/lessons/httpmethods.html)