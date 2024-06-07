# Lab 5

Lab 5 had us use request params to search for "students" by ID:
```ruby
let students = [
    {
      id: 1,
      last: "Last1",
      first: "First1",
    },
    {
      id: 2,
      last: "Last2",
      first: "First2",
    },
    {
      id: 3,
      last: "Last3",
      first: "First3",
    }
];
```
```ruby
fastify.get("/cit/student/:id", (request, reply) => {
    const {id} = request.params;
    for(s of students){
        if(parseInt(id) === s.id){
            reply
            .code(200)
            .header("Content-Type", "application/json; charset=utf-8")
            .send(s);
            break;
        }
    }

    reply
    .code(404)
    .header("Content-Type", "application/json; charset=utf-8")
    .send("Student not found");
    
});
```
<a href="https://joeybez.github.io/joeybezner.github.io/">Back to Home</a>
