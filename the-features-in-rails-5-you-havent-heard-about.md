Title
==

Rails 5 Features You Haven't Heard About

Abstract
==

We've all heard about Action Cable, Turbolinks 5, and `Rails::API`. But Rails 5
was almost a thousand commits! They included dozens of minor features, many of
which will be huge quality of life improvements even if you aren't using
WebSockets or Turbolinks.

This will be a deep look at several of the "minor" features of Rails 5. You
won't just learn about the features, but you'll learn about why they were added,
the reasoning behind them, and the difficulties of adding them from someone
directly involved in many of them.

Details
==

This will focus on the stories behind each of these features, more than what
they are (we have a changelog for that). Specifically this will focus on some of
the stories behind the following features:

- `ActiveRecord::Relation#or`
- `ApplicationRecord::Base`
- Preventing destructive action on databases (you can't accidentally drop your
  production DB by running your tests with `DATABASE_URL` accidentally set
  anymore)
- Versioned migrations (your migrations won't change in behavior between
  versions anymore)
- Support for new datatypes in PG and mysql
- `ActiveRecord::Relation#left_outer_joins`
- `ActiveRecord::Base#selected_fields`
- Changes to AR's Boolean type to match Ruby's semantics
- Allow specifying possible arguments to `ActiveSupport::StringEnquirer`
- And more

Many of these features are going to be huge in the day to day development of
Rails apps, but are hard to find if you don't read the entire changelog.

The audience will leave this talk knowing about many of the new tools in their
toolbelts (or ways that they're protected when they weren't before) after
migrating to Rails 5

Pitch
==

Rails 5 is one of our largest releases ever, and there's a lot of useful
features that might otherwise go unnoticed. I am one of the commiters on Rails,
and was directly involved in many of these changes.
