Title
==

I don't know I'm bad at naming things

Abstract
==

Type casting in Active Record is an integral part of Rails, but very few of us
know how it works and the changes it has gone through. We're going to unravel
the mysteries behind how Active Record type casts anything you give to it. We'll
look at the major changes that happened in Rails 4.2, and show the new API
coming in Rails 5. We'll be discussing the process of cleaning up complex legacy
code. Finally, we'll look at the power of simple, composeable APIs, and how this
affects the future of Rails.

Details
==

The talk will start with a brief walk through of what type casting is, and when
Active Record will type cast your input. We'll look at what the code looked like
in Rails 4.1, and what it looks like in Rails 4.2. The main focus of the talk is
process.

Many people look at the Rails code base and assume that it's too clever, or
they're too inexperienced to understand it. In reality, Rails just a really
large legacy code base. The same challenges and precesses apply here as it would
to anyone's legacy program.

The talk will look at how important test coverage is, and how we can break down
a large sweeping change into trivial, small steps. We'll look at how good object
oriented design can lead to code which is much easier to test, and much easier
to get feedback from your test failures.

Finally, we'll look at the new `attributes` API, which is coming in Rails 5.
It's one of several APIs being introduced which are meant to give greater, lower
level, control over Active Record, and turn off some of the "magic". We'll look
at why this is a good thing, and how building these simple APIs allows you to
compose really powerful high level APIs with only a few lines of code.

The intended audience take-away is primarily geared towards the design of APIs,
and why simple is often better. You can build powerful, complex APIs by
composing simple pieces, and there is a ton of value in making those smaller
pieces accessible as well, like we're doing in Rails 5.

After this talk the audience will have a better understanding of a part of
Active Record that affects every application, and can use that knowledge to
improve their apps.

Pitch
==

This talk involves major changes to a core part of Active Record, intended to
make it accessible by every user of Rails. We will also be looking at new APIs
that will be available for public consumption in Rails 5, which will make
several common patterns much easier, and give much more control over how to
convert custom objects to and from SQL.

What is your involvement?
==

I was the Rails contributor responsible for the majority of these changes
