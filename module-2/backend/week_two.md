## Week Two - Module 2 Recap

Fork or re-pull this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON - YOU are a web developer!!!).

Note: When you're done, submit a PR.


### Week 2 Questions

1. At a high level, what is ActiveRecord? What does it do/allow you to do?

  ActiveRecord is an ORM that allows us to easily access the data in a database by viewing the entries in a database as an object.

2. Assume you have the following model:

```ruby
class Team << ActiveRecord::Base
end
```

What are some methods you can call on `Team`? If these methods aren't defined in the class, how do you have access to them?

  .all, .where, .find, to name a few, these methods are being inherited from ActiveRecord::Base.

3. Assume that in your database, a team has the following attributes: "id", "name", owner_id". How would you find the name of a team with an id of 4? Assuming your class only included the code from question 2, how could you find the owner of the same team?

  Team.find(4).  Owner.find(Team.find(4).owner_id).

4. Assume that you added a line to your `Team` class as follows:

```ruby
class Team << ActiveRecord::Base
  belongs_to :owner
end
```

Now how would you find the owner of the team with an id of 4?

  Team.find(4).owner

5. In a database that's holding students and teachers, what will be the relationship between students and teachers? Draw the schema diagram.

  The relationship would be a many to many.
  A student has_many :teachers, through: :teacherstudents and a teacher has_many :students, through: :teacherstudents, and a teacherstudent belongs_to :teacher, and belongs_to :student.  
  If I were to draw the schema diagram it would have three boxes in a row, the left most would be teachers, the middle teacherstudents and the right most would be students.  A line would be going from the id column of the teachers to a column teacher_id in teacherstudents, and a line would be going from the id column of the students to the column student_id in teacherstudents.

6. Define foreign key, primary key, and schema.

  A foreign key is a key by which a specific row of another table is indicated in a table, so as to to link the data in that row of that table to the current row of the current table.  A primary key is the identifier for a row in a table.  The schema is the blueprint for a database at a given moment, which should show the datatypes and foreign keys contained in each table in the database.

7. Describe the relationship between a foreign key on one table and a primary key on another table.

  A foreign key is a key by which a specific row of another table is indicated in a table, so as to to link the data in that row of that table to the current row of the current table, thus the primary key of the current table row that contains the foreign key can be used to refer to a group of data that is related to the data in another table as referred to by the foreign key.

8. What are the parts of an HTTP response?

  Status, header, body?  I was confused on this before and I can't find the three you all mentioned in class.

### Optional Questions

1. Name your five favorite ActiveRecord methods (i.e. methods your models inherit from ActiveRecord) and describe what they do.

  .all, .where, .order, .find, .pluck.

  .all allows you to refer to all of the instances that have been created of a class.

  .where allows you to find all of the instances of the class that meet the parameters that you set.

  .order allows you to order the instances of a class by the parameters you set.

  .find allows you to find a specific instance of a class using its id with very minimal syntactic work.

  .pluck allows you to return all of the values of a specific column of the table referred to by the class.

2. Name your three favorite ActiveRecord rake tasks and describe what they do.
3. What two columns does `t.timestamps null: false` create in our database?

  created_at and updated_at

4. In a database that's holding schools and teachers, what will be the relationship between schools and teachers?
5. In the same database, what will you need to do to create this relationship (draw a schema diagram)?

  I believe 4 and 5 are effectively answered in question 5 above.

6. Give an example of when you might want to store information besides ids on a join table.

  Perhaps you want to know exactly when the relationship began, so the table also carries a created_at date for the relationship between the two.

7. Describe and diagram the relationship between patients and doctors.

  Doctor has_many :patients, through: :doctorpatients, Patient has_many :doctors, through: :doctorpatients, DoctorPatients belongs_to :doctor and belongs_to :patient.  Respective ids have lines to corresponding columns in doctorpatients table, which contains only those two columns, the doctorpatients table sits between the other two in representation of the fact that they relate to one another only through it.

8. Describe and diagram the relationship between museums and original_paintings.
9. What could you see in your code that would make you think you might want to create a partial?

  If I saw that I was generating the same code in a bunch of my views, I would want to create a partial for that information.  In that way a partial helps keep your views DRY.  Like maybe a footer, header, and nav bar that appear on every page, that should not be repeated on every single page.

### Self Assessment:
Choose One:
* I was able to answer every question without relying on outside resources - I did attempt a search for HTTP Response, but didnt use anything I found as it wasn't help.

* I was able to answer most questions independently, but utilized outside resources for a few
* I was able to answer a few questions independently, but relied heavily on outside resources

Choose One:
* I feel confident about the content presented this week
* I feel comfortable with the content presented this week - I understood the concepts, but need to memorize the process and commands.
* I feel overwhelmed by the content presented this week
* I feel quite lost by the content presented this week
