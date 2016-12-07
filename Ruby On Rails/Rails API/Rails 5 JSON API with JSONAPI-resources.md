# Rails 5 JSON API with JSONAPI-resources Video
[Rails 5 api](https://www.youtube.com/results?search_query=rails+5+api)

Published on Oct 16, 2016

I wanted to try this gem out. Here's a super basic API I created to do just that :)

jsonapi-resources: https://github.com/cerebris/jsonapi-r...

CURL COMMANDS:

// For creating a user:

curl -i -H "Accept: application/vnd.api+json" -H 'Content-Type:application/vnd.api+json' -X POST -d '{"data": {"type":"users", "attributes":{"name":"Consuela"}}}' http://localhost:3000/users

// For creating a post that belongs to contact with id of 1:

curl -i -H "Accept: application/vnd.api+json" -H 'Content-Type:application/vnd.api+json' -X POST -d '{ "data": { "type": "posts", "relationships": { "user": { "data": { "type": "users", "id": "1" } } }, "attributes": { "title": "Laughter Post", "content": "HAHAHA" } } }' http://localhost:3000/posts

    Category
        Education
    License
        Standard YouTube License

