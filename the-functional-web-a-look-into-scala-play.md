Abstract:

In this session, we'll take a look at how Rails could be improved by concepts
used by our functional programming cousins in Scala with the Play framework.
We'll talk about concurrency in Rails, and why having a concurrent server isn't
enough. We'll look at how tightly coupled `ActiveRecord` is to our form builder,
and why that can lead to unexpected results in your code. While we look at the
solutions Play has provided, we'll also look at what the repercussions of
bringing these ideas would be.

Details:

Intended Audience: Rails developers who have worked on at least one non-trivial
Rails application. Audience should be familiar with the Rails stack, as well as
common add-ons such as background workers such as `delayed_job` or `resque`.

Intended takeaway: A functional language is not required to have a functional
way of thinking. We need to evolve in how we handle concurrency. We should make
efforts to decouple ActiveRecord from concerns related to form building. Many of
these changes would be large in scale, and if we start to go down the functional
road, we need to make sure we do it right.

Pitch: Scalability and concurrency are two of the most important topics in
modern web applications. It's no secret that functional languages tend to be
easier to parallelize, which also leads to better scaling. The Play framework
and Scala language have solved several hard problems in ways that could be
brought back to Ruby and Rails. By thinking about validations differently, we
can trivially move much of that work off of our servers and into the browser,
without duplicating our code or losing server-side validation. By dealing with
concurrency at levels higher than the server, we can be non-blocking even to the
point that Node reaches, without sacrificing the structure or flow of our
application.

While we'll be looking at code in Scala and Play, this talk is primarily about
Ruby and Rails, and every point we'll look at is going to be compared to Rails,
with a focus on how we could bring the concepts back to Rails in a "ruby" way.

Outline:

- The web is not the same place it was in 2006
- Changes in how we program, and the technologies we use have created several
  pain points in Rails
- Concurrency
  - What is concurrency?
  - What does concurrency look like in Rails today
    - `gem 'unicorn'`
    - `gem 'delayed_job'`
  - Why isn't this a solution?
  - Example of concurrent but unrelated interactions in Ruby via threads
    - Threads force us to think about order of execution
  - Introduce promises/futures
    - Futures allow us to concern ourselves with transformations and
      relationships between data
  - Issues with futures bubbling up to the controller
    - Have to block before we can render the response
    - We don't want that in our application code
    - Easy to introduce bugs
    - Concerns like timeout should be handled at the server level
  - How do other languages do it?
    - Play's controller syntax
    - Similar interface to Rack
      - Take a request, return a response
    - We can also return a `Future[Response]` instead
  - How can we bring this to Rails?
    - Our API is too far removed from HTTP
      - Methods like `render` mutate the controller
      - No good mechanism to say we're ready to send the response if the
        response is built asynchronously
      - Potential solutions
    - We will break Rack
      - Rack assumes a single synchronous response
      - Potential solutions
    - How does Scala/Play solve this?
- Form Builders
  - `ActiveRecord` is tightly coupled to how our form builder works
    - Example: Unexpected results in the typecasting of boolean columns
  - Encourages all validations to be lumped together, even when they aren't
    always relevant
  - Issues with the `if model.save` style of doing things
  - A look at Play's form builders
    - Object which maps to and from a model
    - Handles simple validations and conversions
    - If the model layer expects an int or boolean, it gets one
    - HTML5 validations get built trivially
    - The same object that builds the form is responsible for interpreting the
      results from that form submitting
  - What does the interaction look like functionally?
    - `FormParams => Either[Model, List[Error]]`
    - Let's represent our code that way
    - If we have validation errors, we don't need the database model
    - If we are valid, we don't need the object that renders errors
  - Libraries that help with this today
- Questions?
