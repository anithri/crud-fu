# crud-fu
## CRUD operations in [react] with... [relay]

Create, Read, Update, Delete.  A very common pattern, with amazingly few great examples of ways to accomplish them.

This is intended to be suites of examples of this pattern fully implemented.  There will be 2 sets of suites, one set for servers implementing on of the apis(rest, graphql, ...) used in the examples. And then a front end intended to use of of the back ends.

### Authors Note

I welcome collaboration, please.  I come from a strong rails background, and my initial work will undoubtably reflect that.  I'm looking forward to learning new ways of doing things.

My intention is to have examples of a basic server, an api schema, and a front end that work together to handle a 3 table datastore.

Without others contributions, this will likely remain in a subset of languages I'm using or are interested in.  Right now that would be Rails and AWS lambda, using REST(ala rails), Swagger and GraphQL, feeding a React front end using relay, apollo, and a rest client to be named(axios) later.

Security has to be demonstrated, but I can't decide if it should be only JWT, or if not, what else. 

## APIs
We will start with three API transports(?), REST, Swagger, and GraphQL.  I'm sure there are others out there, speak up and we'll come up with a plan for them.

### Basic data schema
```yml
adventurer:
  id: uuid
  name: string
  city_id: uuid
  cool_factor: number
  debut_year: integer
team: 
  id: uuid
  name: string
  city: string
  debut_year: integer
  adventurer_ids: [uuid]
## City will only be used for read operations.
city: 
  id: uuid
  name: string
  danger_factor: number
```

## Backends

The backends job is to serve the API and handle data.  The data should persist a while.  Doesn't need to be permanent, but it has to be able to reflect changes back to the user for the duration of the servers uptime.

#### GraphQL
I'm going to start with a serverless version of a graphql server because easy and cheap.  I'll also do a graphql-rails based one.

#### Rails Rest
Straightforward, right off of the scaffold installation.

#### Swagger
Personally not interested in this at the moment, leaving for collaborators and future consideration.

## Frontends
Something in the browser that consumes the api that allows crud on Team and Adventurers, and read on Cities.  There are plently of contenders.

#### React and Relay

#### React and Apollo

#### React and Rest Client (Axios?)


