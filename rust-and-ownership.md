Title
==

Owning Ownership: How Thinking About Ownership Prevents Bugs

Abstract
==

Every method or method we write in Ruby or any other language has some hidden
semantics. Who owns the values passed in? What am I allowed to do with the
values returned? In 2015, Mozilla released the Rust programming language, which
brought to the table ways to represent these "ownership" semantics in programs.

In this talk, we'll take a deep dive into why an innocent looking change like
`@env[PARAMETERS_KEY] ||= {}` to `@env[PARAMETERS_KEY] || {}` can cause subtle
and hard to detect bugs, and how thinking about ownership can help keep these
defects out of Ruby programs.

Details
==

This talk will focus on a bug that was found in RSpec during the migration to
Rails 5. While the topic is about ownership, which is primarily associated with
Rust, the talk itself contains almost no Rust, and focuses on code in Rails and
RSpec. The audience will come away from this talk with a new way to think about
return values and mutability, which they can use to prevent common (and painful
to debug) defects in their code.

We'll start by looking at exactly how the bug manifested, and what it took
to track down. The code change responsible is almost exactly the code in the
abstract (the method in question is `ActionDispatch::Request#path_parameters`).

We'll look at why the change was made, and why it causes problems. Once we
establish the thought process that went into it, we'll briefly take a look at
Rust, and what "ownership" means.

After understanding what owning a value means, and what it means to borrow it,
we'll go through the change made in Rails again, keeping ownership in mind, and
see that the bug would have been impossible. The talk will end with a few other
examples from the Rails codebase, which will be much closer to users' code, and
see how the same concepts can apply there.

Pitch
==

The talk demonstrates some of the problems that come from mutability in OO
languages, while presenting tools that are easier to apply to an existing Rails
app than "never mutate anything" or "switch to Clojure or Haskell". I was
involved in finding and solving this bug when migrating RSpec to Rails 5.
