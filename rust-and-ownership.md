Title
==

Owning Ownership

Abstract
==

Every method or function we write, regardless of language, has some hidden
semantics. Who owns the values passed in? What am I allowed to do with the
values returned? In 2015, Mozilla released the Rust programming language, which
brought to the table ways to represent these "ownership" semantics in programs.

While Rust makes these concepts first class in the language, they exist in every
other language as well. In this talk, we'll take a deep dive into why an
innocent looking change like `@env[PARAMETERS_KEY] ||= {}` to
`@env[PARAMETERS_KEY] || {}` can cause subtle and hard to detect bugs, what new
languages are doing to prevent this, and how a change in our thinking can help
keep these defects out of our programs in any language.
