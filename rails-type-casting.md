Title
==

I don't know I'm bad at naming things

Abstract
==

Active Record may look like magic, but at its core it's just Ruby. We're going
to unravel some of the mysteries behind how Active Record type casts anything
you give to it. We'll look at the major changes that this went through in 4.2,
and the new API coming in Rails 5 to let you hook into this. We'll be discussing
the process of making complex legacy code clean. Finally, we'll look at the
power of simple, composeable APIs, and how this affects the future of Rails.

Details
==

While this will involve a brief walk through of what the type casting code
looked like in 4.1, and what it looks like in 4.2, the main focus of the talk is
process. Many people look at the Rails code base and assume that it's too
clever, or they're too stupid to understand it. In reality, it's just a really
large legacy code base, and the same processes apply here.

The talk will look at how important test coverage is, and how we can break down
a large sweeping change into trivially small steps. We'll look at how good OO
design can lead to code which is much easier to test, and much easier to get
feedback from your test failures.

Finally, we'll look at the new `attributes` API, which is coming in Rails 5.
It's one of several APIs being introduced which are meant to give lower level
hooks into Active Record, and turn off some of the "magic". We'll look at why
this is a good thing, and how building these simple APIs allows you to compose
them into really powerful high level APIs with only a few lines of code.

The intended audience take-away is primarily geared towards the design of APIs,
and why simple is often better. You can build incredibly powerful complex APIs
by composing simple pieces, and there is a ton of value in making those smaller
pieces accessible as well. Hopefully after this talk, the audience will have a
better understanding of a part of Active Record that affects every application,
and can use that knowledge to improve their apps.

Pitch
==

This talk involves some major changes to a core part of Active Record, intended
to make it accessible by every user of Rails. We will also be looking at some
new APIs that will be available for public consumption in Rails 5, which will
make several common patterns much easier, and give much more control over how to
convert custom objects to and from SQL.

What is your involvement?
==

I wrote it.
