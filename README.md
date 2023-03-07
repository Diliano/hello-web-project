## Building Routes Exercise

Work through the following in the project `hello_web_project`.

Create a new route that responds to requests sent with:
  * A method `GET`
  * A path `/hello`
  
It should return the text `'Hello [NAME]'`, where `[NAME]` is replaced by the value of the `name` _query parameter_.

```
# Request:
GET /hello?name=Leo

# Expected response (200 OK):
Hello Leo
```

Make sure your server is running - then, using Postman, check the route is working.

## Building Routes Challenge

Work through the following in the project `hello_web_project`.

Create a new route that responds to requests sent with:
  * A method `POST`
  * A path `/submit`

Here's the expected behaviour of this route:

```
# Request:
POST /submit

# With body parameters:
name=Leo
message=Hello world

# Expected response (2OO OK):
Thanks Leo, you sent this message: "Hello world"
```

Make sure your server is running - then, using Postman, check the route is working.

## Test-driving a Route Exercise

_Work in the same project directory `hello_web_project` for the following exercises._

Use the Design recipe to test-drive the following route:

```
# Request:
GET /names

# Expected response (2OO OK):
Julia, Mary, Karim
```

You should assert that the response status code is `200` and that the response body is the correct string.

## Test-driving a Route Challenge

Test-drive a new route `POST /sort-names` which receives a list of names (as a comma-separated string) and return the same list, sorted in alphabetical order.

Here's a description of the expected behaviour:

```
# Request:
POST http://localhost:9292/sort-names

# With body parameters:
names=Joe,Alice,Zoe,Julia,Kieran

# Expected response (sorted list of names):
Alice,Joe,Julia,Kieran,Zoe
```

## Creating a sequence diagram for a web application - Exercise

Create a sequence diagram of the program you've created in the previous section. Make sure your diagram all includes the following: 
 * The HTTP Client
 * The HTTP Request and the data it contains
 * The HTTP Response and the data it contains
 * The Application class (`app.rb`)

## POST /sort-names Sequence Diagram

![](/sort_names_sequence_diagram.png)