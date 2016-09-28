# Rails API Relationships Diagnostic

**NOTE: I wish I had an hour for this diagnostic; I skipped a lot of the questions
as a result. I feel I could have done a lot better with more time to open up
old trainings and use those examples as a guide.

Place your responses inside the fenced code-blocks where indivated by comments.

1.  Describe a reason why a join tables may be valuable.

```sh
Join tables can be valuable because they can describe a complex relationship
between two entities that have a many-to-many relationship, like `books` and
`borrowers.` A join table could provide data for a third entity that encapsulates
the relationship between books and borrowers, like `loans`, because a borrower
can have (borrow) many books and a book can have (be borrowed by) many borrowers.
More simply put: a join table is a special table that holds references to two
or more tables.
```

1.  Provide a database table structure and explain the Entity Relationship that
describes a many-to-many relationship for `Profiles`, `Movies` and `Favorites`
(Think of Netflix). A `Profile` has a `given_name`, `surname` and `email` and a
`Movies` have `title`, `release_date`, and `length` and `Favorites` would be the
join table with references to `Movies` and `Profiles`.

```sh
create_table
```

1.  For the above example, what needs to be added to the Model files?

```rb
class Profile < ActiveRecord::Base
end
```

```rb
class Movie < ActiveRecord::Base
end
```

```rb
class Favorite < ActiveRecord::Base
end
```

1.  What is the purpose of a serializer? What would our `Profile` serializer look
like to show all movies favorited by a profile on
`http://localhost:3000/profiles/1`

```sh
A serializer describes which attributes and relationships should be serialized.
```

```rb
class ProfileSerializer < ActiveModel::Serializer
end
```

1.  What would the command be to _scaffold_ out a **join table** for Favorites from
the above `Movies` and `Profiles`.

```sh
I am running short on time in this diagnostic, but the template I have from my
class notes is the following:
`bundle exec rails g scaffold <NAME OF NEW TABLE> <ATTRIBUTE:DATA-TYPE>
<NAME OF NEW COLUMN:REFERENCES> <NAME OF COLUMN TO BE REFERENCED: REFERENCES>
```

1.  What is `Dependent: Destroy` and where/why would we use it?

```sh
You would use `Dependent: Destroy` when you wanted to destroy all the data that
was associated with (or dependent on) some data that you wanted to destroy. For
example, if you wanted to destroy the record of a patient at a clinic because
that patient moved away (or some other reason), you would also want to destroy
all the appointment data related to (or dependent on) that patient--depending on
how you set up the relationships in your app.
```

1.  Think of **ANY** example where you would have a one-to-many relationship as well
as a many-to-many relationship in an application. You only need to list the
description about the resources and how they relate to one another.

```sh
I'm not sure I understand the question correctly, but if I do:
Netflix is an example of the above question: a USER can have many PROFILES (a
one-to-many relationship), and each PROFILE can have many MOVIES listed
in their queue (a many-to-many) relationship.
```
