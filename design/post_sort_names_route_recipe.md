# POST /sort-names Route Design Recipe

_Copy this design recipe template to test-drive a Sinatra route._

## 1. Design the Route Signature

You'll need to include:
  * the HTTP method
  * the path
  * any query parameters (passed in the URL)
  * or body parameters (passed in the request body)

Method: POST
Path: /sort-names
Body parameter: names (string)

## 2. Design the Response

The route might return different responses, depending on the result.

For example, a route for a specific blog post (by its ID) might return `200 OK` if the post exists, but `404 Not Found` if the post is not found in the database.

Your response might return plain text, JSON, or HTML code. 

_Replace the below with your own design. Think of all the different possible responses your route will return._

```

When body parameter 'names' is Joe,Alice,Zoe,Julia,Kieran

=> Alice,Joe,Julia,Kieran,Zoe

```

## 3. Write Examples

_Replace these with your own design._

```
# Request 1:

POST /get-names
Body parameter => names: Joe,Alice,Zoe,Julia,Kieran

# Expected response:

=> Alice,Joe,Julia,Kieran,Zoe

# Request 2:

POST /get-names
Body parameter => names: Dilan,Joe,Alice,Zoe,Julia,Kieran

# Expected response:

=> Alice,Dilan,Joe,Julia,Kieran,Zoe

```

## 4. Encode as Tests Examples

```ruby
# file: spec/integration/app_spec.rb

require "spec_helper"

describe Application do
  include Rack::Test::Methods

  let(:app) { Application.new }

  context "POST /sort-names" do
    it "returns a sorted list of names given" do
      response = post("/sort-names", names: "Joe,Alice,Zoe,Julia,Kieran")

      expect(response.status).to eq 200
      expect(response.body).to eq "Alice,Joe,Julia,Kieran,Zoe"
    end
    it "returns a sorted list of names given" do
      response = post("/sort-names", names: "Dilan,Joe,Alice,Zoe,Julia,Kieran")

      expect(response.status).to eq 200
      expect(response.body).to eq "Alice,Dilan,Joe,Julia,Kieran,Zoe"
    end
  end

end
```

## 5. Implement the Route

Write the route and web server code to implement the route behaviour.
