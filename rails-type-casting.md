Title
==

Designing a Great Ruby API - How We're Simplifying Rails 5

Abstract
==

The most useful APIs are simple and composeable. Omnipotent DSLs can be great,
but sometimes we want to just write Ruby. We're going to look at the process of
designing a new API for attributes and type casting in Rails 5.0, and why
simpler is better. We'll unravel some of the mysteries behind the internals
After all, Rails is ultimately just a large legacy code base.

In this talk you'll learn about the process of finding those simple APIs which
are begging to be extracted. You'll learn the refactoring process that can be
used to tease them out slowly. And you'll be getting a sneak peak at several of
the features coming in Rails 5.0.

Details
==

The talk will start with a brief walk through of what type casting is, and when
Active Record will type cast your input. Then we'll look at the API we wanted to
have to hook into this process. The focus for the design of the attributes API
was simplicity, and composeability. It quickly became apparent just how many
other parts of Active Record were something that can be described in terms of
this new API.

Many people look at the Rails code base and assume that it's too clever, or
they're too inexperienced to understand it. In reality, Rails just a really
large legacy code base. The same challenges and precesses apply here as it would
to anyone's legacy program.

The talk will look at how important test coverage is, and how we can break down
a large sweeping change into trivial, small steps. We'll look at how good object
oriented design can lead to code which is much easier to test, and much easier
to get feedback from your test failures.

As we look at the attributes API as our example of this process put into
practice, we'll talk about the focus on adding lower level APIs in Rails 5,
where you can turn off the magic. We'll discuss why this is a good thing, and
how easy it becomes to compose them into powerful, high level APIs with only a
few lines of code.

The audience take-away will be focused on API design and process. They will
learn about the process that we went through to identify this API, and how we
spotted all of the other APIs which were using this common concept, but didn't
have a name for it.

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
