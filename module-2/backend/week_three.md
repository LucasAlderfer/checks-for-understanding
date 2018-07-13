## Week Three Recap

### Instructions
Fork this repository. Be sure to pull the latest changes to your local repo. Answer the questions to the best of your ability.

Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR with a reflection in the comments about how this exercise went for you.

### Week 3 Questions

1. What is the entry at the command line to create a new rails app?
  rails new project -T -d='postgresql' --skip-turbolinks --skip-spring
2. What do Models generally inherit from in rails?
  Models generally inherit from ApplicationRecord in rails.
3. What do Controllers generally inherit from in a rails project?
  ApplicationController
4. How would I create a route if I wanted to see a specific horse in my routes file assuming I'm sticking to standard conventions and that I didn't want other CRUD functionality?
  resources :horses, only: [:show]
5. What rake task is useful when looking at routes, and what information does it give you?
  rails routes, it gives you a list of all the routes currently listed in your config routes file and the controller and controller method that the route uses and what HTTP verbs can be used through that path.
6. What is an example of a route helper? When would you use them?
  A route helper would be something like horse_path(horse) instead of /horses/:id.  You would use them anytime you were going to have to specify a route for a test or a redirect.
7. What's the difference between what `_url` and `_path` return when combined with a routes prefix?
  `_url` makes the link the entire URL where as `_path` makes the link just a local path.
8. What are strong params and why are they necessary?
  Strong params are parameters that are specifically found and allowed before being passed into a view and they are important in order to control what information a viewer of a page may end up having access to.
9. What role does `form_for` play in helping us create our forms?
  form_for allows us to create a form to fill in information for a specified object to pass the parameters from the form into an object rather than just have the entries live in the params.
10. How does `form_for` know where to submit the user's input?
  form_for knows where to submit the user's input because you tell it what the form is for at the beginning, hence form for.
11. Create a form using a `form_for` helper to create a new `Horse`.
  <%= form_for @horse do |f| %>
    <%= f.label :name %>
    <%= f.text_field :name %>

    <%= f.submit %>
  <% end %>
12. Why do we want to validate our models?
  We need to validate our models to make sure that they require the inputs we want so that we do not end up throwing errors when an entry has been created that cannot access all the methods we might call on it.
13. What are the steps of the DNS lookup?
  browser
  name resolving server
  root
  top level domain
  authoritative name server

### Review Questions
14. How would you call the method `prance` from within the method `move` on a `Horse` instance?
  I could call prance in def move.  so Horse.move but:
  def move
  prance
  end.
15. Given the following hash:

```ruby
furniture = {table: {height: 3, color: "red"}, purchased: true}
```
What is the different between how you would return true vs returning 3?  
  true: furniture[:purchased], furniture[:table][:height]
16. What is inheritance?
  Inheritance is where one object takes on the characteristics or abilities of another.

### Self Assessment:
Choose One:
* I was able to answer every question without relying on outside resources - Check
* I was able to answer most questions independently, but utilized outside resources for a few
* I was able to answer a few questions independently, but relied heavily on outside resources

Choose One:
* I feel confident about the content presented this week - check
* I feel comfortable with the content presented this week
* I feel overwhelmed by the content presented this week
* I feel quite lost by the content presented this week
