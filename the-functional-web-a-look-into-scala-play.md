Abstract:

Scala is a popular Functional OO Hybrid language that runs on the JVM. It’s Play framework is heavily inspired by Rails, but the functional language beneath it leads to many new and interesting concepts. We’ll explore the differences in data flow from form to database, how monads can make concurrency trivial (taking it even farther than Node.js), how the actor model lets you have background workers without Redis, and why you don’t actually need an ORM.

Details:

Intended Audience: Rails developers who have worked on at least one non-trivial Rails application. Audience should be familiar with the Rails stack, as well as common add-ons such as background workers such as delayed_job or resque.

Intended takeaway: The play framework handles several key concepts in ways that could potentially improve Rails. A functional language is not required to have a functional way of thinking about problems. Always be exploring new ideas (but bring what you learn back to Ruby and Rails).

Pitch: Scalability and concurrency are two of the most important topics in modern web applications. It’s no secret that functional languages tend to be easier to parallelize, which also leads to better scaling. The Play framework and Scala language have solved several hard problems in ways that could be brought back to Ruby and Rails. By thinking about validations differently, we can trivially move much of that work off of our servers and into the browser, without duplicating our code or losing server-side validation. By dealing with concurrency at levels higher than the server, we can be non-blocking even to the point that Node reaches, without sacrificing the structure or flow of our application.

Outline:
- A brief look into Scala
  - Familiar syntax
  - Static typing
  - Singleton object synatax

- Controllers
  - Similar concepts to Rails
  - URI parameters are explicitly passed as method arguments, rather than
    implicitly in a params hash
  - Actions take in a request, and return a response
  - The simplest case looks like this: def hello = Action { Ok("Hello, world") }
  - More aware of HTTP
  - Very little boilerplate
  - Quite similar to using Rack, but with a nicer DSL
  - Responses are immutable. Methods like `with_headers` return a new response
    object
  - Works well with the middleware pattern

- Forms
  - Models don't know anything about validation or persistence in Play
  - Functional programming flows as a transformation of data, rather than
    changes in state
  - In Rails, we grab the request data, give it to the model, and ask if it's
    valid. The same model is used to display errors, even though what we're
    populating the form with is the request data given
  - Forms in Scala take in the request data, and will give back either a model
    (if the data is valid) or a form with errors (if it was not)
  - Keeps validation of user input in classes that are meant to deal with user
    input
  - Since the same object is used to construct the forms in the HTML, adding
    client side validation via HTML5 is trivial
  - Certain additional steps are required to keep code clean when dealing with
    validations that cannot be validated at point of input. (Uniqueness is the
    big one. We don't have the half-way doesn't actually validate uniqueness
    type validator).

- Concurrency
  - Brief overview of what monads are, describing them in terms of Enumerable
    (which is a monad in Ruby)
  - Future is the monad of concurrency, similar to promises in JavaScript, but
    following the same interface as other monads.
  - Controller actions are either synchronous or asynchronous
  - The only change required to make an action asynchronous is calling
    `Action.async` instead of `Action` and returning a `Future[Response]`
    instead of a `Response`
  - Enables us to reach node-like levels of asynchronous
  - Many things are automatically wrapped in a `Future` for you, like network
    IO.
  - Since we have no GIL on the JVM, threads are universally used over forks
  - This, combined with immutability make dealing with concurrency trivial,
    without having to significantly alter the flow of the application

- No ORM
  - This is not as painful as it sounds
  - Scala's language semantics give us the nice parts of model creation, and
    updating attributes
  - Several DSLs to choose from for constructing queries in Scala
  - What don't we need from `ActiveRecord`?
    - Query construction - Handled elsewhere
    - Validations - Handled elsewhere
    - Attribute assignment - Handled elsewhere
    - Callbacks - Can we deprecate those already?
    - Large ambiguous tables required to determine if an associated record will
      also be saved
  - What's left that we actually want?
    - Automatic assignment of IDs
    - Timestamps
  - Not really that hard to add those two by hand, or automatically with macros.
  - Some of the more niche but useful features like `counter_cache` can be added
    in by libraries
  - Most of what `ActiveRecord` provides isn't very hard to replace by being
    just a tad more explicit.
  - Our construction of HTML forms is no longer tightly coupled to our database
    interaction library
