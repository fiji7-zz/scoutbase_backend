# Back-end task of Code Challenge for Scoutbase

This task is for demonstrating your understanding of HTTP, GraphQL, Node.js and general API practices.

Instructions:

1. Implement a Node.js-based server with raw `http`, Koa or Express.
2. Add a `/graphql` endpoint serving the apollo-server or any other GraphQL implementation.
3. Schema must be able to return proper response for the following public query:

```graphql
{
  movies {
    title
    year
    rating
    actors {
      name
      birthday
      country
      directors {
        name
        birthday
        country
      }
    }
  }
}
```

4. Add support for the following mutation:
```graphql
mutation createUser($username: String, $password: String) {
  createUser(username: $username, password: $password) {
    token
    user {
      id
      name
    }
  }
}
```

5. To expand on the number four, add a mutation-based authentication that accepts:
```graphql
mutation login($username: String, $password: String) {
  login(username: $username, password: $password) {
    token
    user {
      id
      name
    }
  }
}
```

6. Authenticated users may request additional fields for the query used earlier. New `scoutbase_rating` field must return the a random string between 5.0-9.0:

```graphql
{
  movies {
    scoutbase_rating

    title
    year
    rating
    actors {
      name
      birthday
      country
      directors {
        name
        birthday
        country
      }
    }
  }
}
```

7. `/graphql` must be accessible for external clients.

8. End.

How to run 

1. npm i
2. create a database in the pgAdmin
3. create ".env" file
4. put properties from the pgAdmin to ".env" file just like in ".env.example" file
5. npm start