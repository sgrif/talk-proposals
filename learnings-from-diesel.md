Title
==

Databases: What We Can Learn From Other Languages

Abstract
==

Learning new languages can broaden our horizons and help us think about problems
in different ways. This is even more true for frameworks. In this talk, we'll
take a look at Diesel, an ORM and Query Builder written in Rust. We'll compare
its similarities and differences to Active Record, and look at how its solutions
to some hard problems can be applied in our Ruby code.

In this talk you'll learn about how some of Active Record's internals work.
You'll also learn about common mistakes that Rails users make, and how to avoid
them. You don't need to know Rust to attend this talk

Details
==

While this talk will involve Rust code, it will primarily be focused on Active
Record, and how to more effectively use it in Rails apps.

We'll start by looking at what Active Record provides at a very high level.
Specifically, we'll focus on the "most useful" features -- or the features that
are most missed when using other libraries. We'll then start to look at why some
of the problems it solves are hard.

We'll then look at what some of the same features look like in Diesel (Rust's
ORM), and how it goes about solving these problems, and contrast it with Active
Record.

Specifically we'll look at the flaws in each library's approaches, and the
common problems that they cause in apps. We'll look at this from several angles:

- When they make app code become overly complex or hard to maintain
- Why they make it easy to accidentally introduce bugs
- When they are a common source of bugs in the framework itself

We'll then start to look at using Active Record, thinking about some of Diesel's
approaches, and how it solves some of these common problems. We'll also look at
ways that Active Record is actively learning from Diesel, and using it to
improve itself.

The audience will leave this talk with a better understanding of Active Record,
and ORMs in general, and knowledge they can use to improve their apps at their
day to day jobs

Pitch
==

Active Record accounts for 210KLOC of Rails' 270KLOC codebase. It is the most
useful piece of Rails, and the most common source of issues. It has several
fundamental flaws in its design that we can see other libraries working around.
Thinking about it from another angle can vastly improve every users' code base.

I am qualified to speak about this because I am the maintainer of both Active
Record and Diesel.
