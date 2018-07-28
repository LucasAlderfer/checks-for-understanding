### Week 5 Questions

Re-pull from this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON!).

Note: When you're done, submit a PR.

### Week 5 Questions
1. How do we make flash messages display on a page?
  flash[:notice] = "your message" in the controller, and then a piece of code in your application.html.erb above the yield in your body that displays flash messages at the top of the page for each page.

2. Where is cart information/temporary information usually stored?
  In a session.

3. What might be some reasons not to store a cart in our database? Are there any reasons why we would want to persist that information?
  Might not store a cart in the database because it might take up a lot of room on the server, and this way we can push off the onus of storing that data on the user.  We might want to persist that data so that if you logout or if you login on a different computer, you might want to still be able to access a cart that you had not yet checked out.

4. What is the purpose of the asset pipeline?
  To concatenate, minify, precompile, and fingerprint our code for us.

5. Why do we precompile our assets?
  We precompile our assets to lessen the load on the server

6. What do each of the following tags do?

  One links a stylesheet to a view, another links a javascript file to a view, the third references an image in a view.

```ruby
<%= stylesheet_link_tag "application" %>
<%= javascript_include_tag "application" %>
<%= image_tag "rails.png" %>
```

7. What are some of the elements of a great read me? What are some of the benefits of taking the time to update a readme for our project?
  A great readme should explain what someone needs for your code to work, what it is supposed to do, how to use it, and explain something of what it is doing to do what it does (kind of a 30k foot how this works).  The benefits of a good readme are that people looking at your project might be more likely to try it if they can understand easily what it does, and what it is for, and how it was made.  Particularly potential future employers may be more easily to see how skilled we are if we can make clear what we made code to do and that we did it properly.

8. What are the top four accessibility issues that we as developers should be aware of?
  From what I can find online the most common web accessibility issues are:
    Navigation
    Site Structure
    Text
    Images
    Hyperlinks
    Multimedia
    Forms

9. `before_save` is an example of a what? Where in our Rails application would we find a `before_save`?
  Before_save is a callback and we might find a before_save in the application controller of our app to ensure something before we save or update things in our database.

10. Given the following object, how would we create a scope for all users who are active?

```ruby
User.create(name: "Happy", active: true)
```

scope: :active, -> {where(active:true)}

11. What is the difference between a scope and a class method?
  Scopes appear to reduce the number of objects within a class that will be acted upon, whereas a class method acts on the whole class.

### Review Questions:  
12. Given the following hash:  

```ruby
{cart: {"17" => 4, "204" => 52, "29" => 22}}
```

  12a. How would you add item with id of 48 with a quantity of 4?     [:cart]['48'] = 4
  12b. How would you increase the quantity of item 29?    [:cart]['29'] += 1
  12c. How would you find out how many items your user is thinking about purchasing?   [:cart].count  

13. What is polymorphism? How does it relate to duck-typing? What are two ways you use this in everyday Rails applications?
  From what I can tell, polymorphism appears to be a lazy way of creating relationships in a database without having to create an explicit relationship to different other tables.  It relates to duck-typing because they are both ways of just getting the thing to work without knowing explicitly what you are doing.  ActiveRecord and Routes, but I'm guessing if I knew how to use them better, they wouldn't be so duck typed.

14. How would you clean the string "(630) 854-5483" to "630.854.5483"?  
  So, it looks like in ActiveRecord I could use:
  number_to_phone("(630) 854-5483".delete("^[0-9]"), delimiter: ".")

### Self Assessment:
Choose One:
* I was able to answer every question without relying on outside resources
* I was able to answer most questions independently, but utilized outside resources for a few
* I was able to answer a few questions independently, but relied heavily on outside resources - Remember Ruby, Poros and Carts, Callbacks, Asset Pipeline for a few minutes and then mostly how to deploy production to heroku, 30 minutes to read articles on good readmes but 2 of the links do not work.  This CFU felt like it was written for a week that included several lectures we didn't have.

Choose One:
* I feel confident about the content presented this week
* I feel comfortable with the content presented this week - I feel comfortable with the content presented this week, but this CFU made me feel as though there is some content I am expected to know that was not presented this week.
* I feel overwhelmed by the content presented this week
* I feel quite lost by the content presented this week
