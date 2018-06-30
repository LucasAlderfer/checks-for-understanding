## Week One - Module 2 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON!).

Note: When you're done, submit a PR.

### Week 1 Questions

1. List the five common HTTP verbs and what the purpose is of each verb.

  GET: Used to render a page
  PUT/PATCH: Used to update a page
  POST: Used to create a page
  DELETE: Used to delete a page

2. What is Sinatra?

  Sinatra is a Ruby API used to create web apps.

3. What is MVC?

  MVC is the design convention for our files when create web apps whereby we have Models, Views and Controllers, with the controller acting as the overarching logic that communicates with the views that hold our presentation and the models that hold the data logic.

4. Why do we follow conventions when creating our actions/path names in our Sinatra routes?

  We follow conventions when creating our actions/path names in Sinatra routes because we want our users to see that they are going where they expect to be going, **but also because interactions between and clients are stateless and the REST convention helps us to work with state in HTTP.**

5. What types of variables are accessible in our view templates without explicitly passing them?

  Instance variables

6. Given the following block of code, how would I pass an instance variable `count` with a value of `1` to my `index.erb` template?

  ```ruby
  get '/horses' do
    erb :index
  end
  ```
  create a line of code above 'erb :index' that reads '@count = 1'

7. In the same code block, how would I pass a local variable `name` with a value of `Mr. Ed` to the view?

  create a line of code above 'erb :index' that reads "@name = 'Mr. Ed'"

8. What's the purpose of ERB?

  ERB allows us to create pages that are HTML with embedded Ruby functionality so that we can use ruby functions on our objects in our display for things like enumerators and instance methods that become more dynamic if they function off of an interaction with the data using ruby functions.

9. Why do I need a development AND test database?

  You need a development and a test database so that when you run your tests you do not need to run your tests according to all the data in your database and control exactly what data lives inside of the test database at any given time, while still being able to run your app with a development database to be able to see the way your app works with a more realistic amount of data that you do not need to create from scratch.

10. What is CRUD and why is it important?

  CRUD is Create, Read, Update and Destroy, which is the operations that you want to be able to preform on a resource, and it is important because CRUD functionality allows you and your user to properly manipulate the data in their database.

11. What does HTTP stand for?

  Hypertext Transfer Protocol

12. What are the two ways to interpolate Ruby in an ERB view template? What's the difference between these two ways?

  <%= ruby code here %> and <% ruby code here %>, the first displays on the page whatever the return value of the code is, they second runs the code but does not display it there, presumably so that it can give us values we are using to display elsewhere.

13. What's an ORM? What does it do?

  Object Relational Mapper, it allows us to turn rows of databases into objects in order for us to be able to more easily manipulate the data in the database with an Object Oriented Programming language.

14. What's the most commonly used ORM in ruby (Sinatra & Rails)?

  ActiveRecord

15. Let's say we have an application with restaurants. There are seven verb + path combinations necessary to provide full CRUD functionality for our restaurant application. List each of the seven combinations, and explain what each is for.

  GET '/restaurants' do
    erb :'/restaurants/index'
  end
  This allows us to render the index page when visiting the listed path.

  POST '/restaurants/:id' do
    erb :'/restaurants/show'
  end
  This allows us to create new restaurant pages

  PUT '/restaurants' do
    erb :'/restaurants/index'
  end
  This allows us to update our index page (like when we have added a new restaurant and want it to appear).

  DELETE '/restaurants/:id' do
    erb :'/restaurants/index'
  end
  This allows us to remove restaurant pages and sends us to the index once we have.

  GET '/restaurants/new' do
    erb :'restaurants/new'
  end
  This allows us to render the new restaurant page when we go to restaurants/new.

  GET '/restaurants/:id/edit' do
    erb :'restaurants/edit'
  end
  This allows us to render the edit restaurant page when we go to restaurants/some id/edit.

  GET '/restaurants/:id' do
    erb :'/restaurants/show'
  end
  This allows us to visit restaurant pages to see the page for a specific restaurant.


  All together this properly allows us to Create pages, read our pages and our index, update our pages and index, and destroy pages.


16. What's a migration?

  A migration is an interaction between a database and your app that shows how objects will be created from that database.

17. When you create a migration, does it automatically modify your database?

  No.

18. How does a model relate to a database?

  A model relates to a database by providing rules for the way that the data should be structured when the database is migrated.

19. What is the difference between `#new` and `#create`?

  '#new' creates a new instance of the class in your database but it does not save it, and '#create' does both.


### Review Questions:  
20. Given a CSV file (“films.csv”) with these headers [id, title, description], how would you load these into your database to create new instances of Film?  

CSV.foreach('films.csv', headers: true, header_converters: :symbol) do |row|
  Film.create(id: row[0], title: row[1], description: row[2])
end

21. Given the following hash:
```
activities = {
  hiking: {cost: $0, supplies: ['hiking shoes', 'water', 'compass']},
  karaoke: {cost: $10, supplies: ['courage', 'microphone']},
  brunch: {cost: $35, supplies: ['mimosa flutes']},
  antiquing: {cost: $200, supplies: ['list of antique stores']}
}
```
How would I add 'granola bar' to things you should have when hiking?

activities[:hiking][:supplies] << 'granola bar'

22. What are the 4 Principles of OOP? Give a one sentence explanation of each.

Encapsulation

**Encapsulation is the mechanism of hiding of data implementation by restricting access to public methods.**

Abstraction

Abstraction is effectively setting up a set of rules such that different objects can know things about the way other objects work without actually knowing anything about them.

Inheritance

Inheritances allow one object to a specific version of a larger group and thus have characteristics of the group while being distinct.

Polymorphism

**It means one name many forms. It is further of two types - static and dynamic. Static polymorphism is achieved using method overloading and dynamic polymorphism using method overriding.**



### Self Assessment:
Choose One: (erase the others)
* I was able to answer every question without relying on outside resources

* I was able to answer most questions independently, but utilized outside resources for a few - This one, **formatted** when coming directly from outside source.

* I was able to answer a few questions independently, but relied heavily on outside resources

Choose One:
* I feel confident about the content presented this week
* I feel comfortable with the content presented this week
* I feel overwhelmed by the content presented this week - I can't quite say I am comfortable yet, but by the end of the day on Friday I felt I was strongly trending towards comfortable with a few sticky spots.
* I feel quite lost by the content presented this week
