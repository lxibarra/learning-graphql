# Learning GraphQL

* Run ```npm install```
* in one terminal run npm run json:server
* open a second terminal and run ```npm run dev```
* Open your browser http://localhost:4000/graphql
* To view the mocked API go to http://localhost:3000/users or http://localhost:3000/companies

Make sure you update the db.json file as needed.

## Query's ##

### Get a graph by user ###
We can request data about a user and nested resources such as company data.
```javascript
query {
  user(id:"23") {
    id
    firstName
    age
    company {
      name
      description
    }
  }
}
```

### Get a Graph by company ###
We can request data about a company and drill down to the users in it.
```javascript
query {
  company(id:"1") {
    name
    users {
      id
      firstName
      age
    }
  }
}
```

## Mutations ##

### Add new users ###
Creates a POST request to json-server
```javascript
mutation {
  addUser(firstName:"Rolando", age:23, companyId:"2") {
    id
  }
}
```

### Update users ###
Creates a patch request to update only the fields in the payload.
```javascript
mutation {
  updateUser(id:"48", firstName:"Jona") {
    id
    firstName
    company {
      name
    }
  }
}
```

### Delete users ###
Creates a delete request to eliminate a record.

```javascript
mutation {
  deleteUser(id:"B1mO9bAmZ") {
    id
  }
}
```
