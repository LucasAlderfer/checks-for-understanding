## Week Four Recap

### Instructions
Fork or re-pull this repository. Answer the questions to the best of your ability.

Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR with a reflection in the comments about how this exercise went for you.

### Week 4 Questions

1. What is a cookie?
  A cookie is data about a user's preferences on that site.
2. What’s the difference between a session and a cookie?
  A session is stored on the server side, and cookies are stored on the user's browser.
3. What’s a flash and when do you want to use flashes?
  A flash is a message that appears on a page when a user visit's it due to a certain condition.  You use them to alert a user as to the effects of their recent actions.
4. Why do people say “HTTP is stateless”?
  Because HTTP does not know anything about your history or preferences, those must be stored in cookies and sessions and user account data etc.
5. What’s authentication? Explain.
  Authentication is a site's way of figuring out who is accessing the site from your browser, usually using passwords.
6. What’s the difference between authentication and authorization?
  Authorization is different than authentication because it is the restriction or allowance to visit certain pages on a site based on the authentication.
7. What’s a before filter?
  A before filter is a method that runs before each action in a controller to confirm something about the user before allowing the action to occur.
8. How do we keep track of a user once they’ve logged in?
  We keep track of a user once they have logged in by way of sessions.
9. When do you want to namespace a resource? When do you want to nest a resource? What's the differences between those two approaches?
  You namespace a resource when you want to be able to exert more control over who is able to access that resource as a whole.  Nested resources are for when access to a resource is only possible through another resource due to their connection.
10. At a high level, what tools can you use to implement authorization? How would you use them?
  You can create before filters to check the current user and to check if they are an admin at the controller level using session data.  You can also namespace a resource to ensure that the resource would only be accessible to someone who was an admin using filters again to check the role of the user.
11. What's an enum, and what advantages does it offer? What data type needs to be in your database to use an enum? Where do you declare an enum?
  Enum's allow one to set up a column in a table as an integer but still return a string when the instance method for the attribute is called in a view.  This is advantageous because integers are much smaller to store than a string and faster to check.  Enum's are declared in the model for the object.
12. What are some strategies you can use to keep your views DRY?
  Somethings, like a nav bar can be placed into the application.html.erb in order to allow them to show up on every page without including the code on every page, you could include basic nav and cart functionality here, you can also place the code to implement flash messages here.  You can also use helper methods in order to define some of the information you want available in your views.


### Reviews Questions
13. Given the following array of hashes, how would I print an alphabetical list of holidays?
```ruby
[
 {holiday: {name: "St Patrick's Day", supplies: ["Corned Beef and Cabbage"]}},
 {holiday: {name: "Halloween", supplies: ["Candy", "Costume"]}},
 {holiday: {name: "Hanukkah", supplies: ["Menorah"]}}
]
```
  order([:holiday][:name]).pluck(:name)  (?)
  Hard without being able to play with it in a rails project.  

14. How would you clean incoming data to ensure "$300" or "300.00" is stored as 300?
  Use '.to_i'?

### Self Assessment:
Choose One:
* I was able to answer every question without relying on outside resources
* I was able to answer most questions independently, but utilized outside resources for a few - this
* I was able to answer a few questions independently, but relied heavily on outside resources

Choose One:
* I feel confident about the content presented this week
* I feel comfortable with the content presented this week - this
* I feel overwhelmed by the content presented this week
* I feel quite lost by the content presented this week
