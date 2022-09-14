# GRAPHQL PART 1

# OVERVIEW ABOUT GRAPHQL
## WHAT IS A GRAPH QL ?
It is a query language for an underlying API
Unlike other API it need not have different endpoints for different activities.
There can be different actions such as Create, Read, Update or Delete to be done on a single Endpoint.

## SCHEMA
The System of defenition to be written, or the Schema that is to be followed here is called as
"SCHEMA DEFENITION LANGUAGE" (SDL)

## OPERATIONS
QUERY => a READ only operation
MUTATION => an operations that modifies value
SUBSCRIPTION => A long lived operation that fetches response for the subscribed source events.

## GRAPHQL DOCUMENTS
A graphql document may contain one or more of these operatoins like
 multiple :
 - queries
 - mutations
 - subscriptions

Mutation queries modify data in the data store and returns a value
Fields describe a piece of data in the data store and returns a value
Directives are identifiers that add additional functionality without affectin the value of the response but can affect
what response comes back to the client.

# INTROSPECTION QUERIES
A graphQL language, supports introspection over the schema using the same GRAPHQL language.
The following are the introspection queries on the Query operation type :
__schema
__type
__typename

```
Note : ALl introspection queries starts with "__"(2 underscores
```

# ATTACKS IN GRAPHQL
Unauthenticated access to the Graph ql endpoint
Introspection queries are enabled
GraphQL available in debug mode
Application level DOS
SQL injection
IDORs
Data exposure through error messages
MISC. GraphQL attacks

# REFERENCES
https://graphql.org/learn/
https://hasura.io/learn/graphql/intro-graphql/introspection/
