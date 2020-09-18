1. Write a test
1. Create the model (if it doesn't exist)
1. Create a migration that creates the database and attributes (if it doesn't exist)
1. Create the route for your feature test
1. Create the controller that is associated with the route
1. Create the controller action that is associated with the route
1. Create the view for the controller action
1. Fill the view with the DB data
1. Fill in the controller action with a database query (.all, etc)
1. ?????
1. Profit

## HOW TO START:
1. How to create a rails app from scratch: 
```
rails _5.1.7_ new myapp -T --database=postgresql --skip-spring --skip-turbolinks
rails _5.1.7_ new myapp -api -T --database=postgresql --skip-spring --skip-turbolinks
```
2. git init/add/commit - "Initial commit"
3. Configure the database 
```
rake db:created
```
4. `rails s` to launch the server http://localhost:3000  
5. Add your gems to Gemfile only to development/tests because these help us test when we're developing. When we deploy to heroku, we don't need our testing environment. Here are some:
    * **rspec-rails** - the test suite
    * **capybara** - gives us tools for feature testing
    * **launchy** - allows us to use save_and_open_page so that when you put that in our code, when it hits, it'll generate a new browser with our code so that we can look at it. It's a little slow and should be use as the last line when you can't figure out why something isn't working the way you expected it to.
    * **pry** - debugging tool
    * **simplecov** - test coverage testing validations and relationships on models
    * **active_designer** - give you a visual of the current structure of your database
    * **nyan-cat-formatter** - for test funsies
6. Run `bundle install`
7. Rspec setup run `rails g rspec:install`
8. Shoulda-matchers setup in rails_helper.rb: 
```
Shoulda::Matchers.configure do |config|
        config.integrate do |with|
          with.test_framework :rspec
          with.library :rails
        end
      end
 ```
9. In rails_helper.rb
  - Configure SimpleCov 
  ```
  require 'simplecov'
    SimpleCov.start
  ```
  - Add "--format NyanCatFormatter" to .rpsec
10. Directory setup
    ```
    mkdir spec/models spec/features
    ```
    ```
    touch spec/models/.keep spec/features/.keep
    ```
11. ALWAYS CHECKOUT TO A NEW BRANCH PER FEATURE/FUNCTIONALITY
12. 2 types of tests:
  - Model tests `touch spec/models/object_spec.rb` always have to add `_spec.rb` for it to work. Object is just an example of an object - this will be whatever we are working with. In this file we have to `require "rails_helper"`. Have to do it for every _spec.rb_ file.
    - For a **model** we need the relationship and validation tests and any other helper methods we write.
  - Feature tests: should follow CRUD (index, create, new, show, update, destroy specs)! Here we test all of the feature tests from the user stories for functionality of our page.
13. Run `rspec` to see what happens
**YOU HAVE TO READ THE ERRORS, SOMETIMES IT'LL SAY THERE ISN'T A DATABASE, SOMETIMES IT DOESN'T HAVE A CONSTANT ARTICLE, SOMETIMES IT'LL SAY THAT THE DATABASE ISN'T A TABLE AND YOU HAVE TO DO A MIGRATION.**
- usually you get an error because you don't have a database so you'll have to run `rails db:create` then do this to create a migration `rails g migration CreateObjects title:string body:text` to create a db resource table with specific attributes and a db that is a  migration when you want to use it for a cloud. You have to run a rails db:create at the beginning to even create a database, then again to create the test and development databases.

## Model
1. Run rspec if we get an error similar to this
    * `An error occurred while loading ./spec/models/object_spec.rb.` we need to make a model
    * `Uninitialized Constant Object` - we have to make a model!
2. We have to create the object/model of what we're trying to create (object) `touch app/models/object.rb`
3. Add this to create the model/object:
```
class Object < ApplicationRecord

end
```
4. Make sure application_record.rb has this in it: 
```
class ApplicationRecord < ActiveRecord::Base
     self.abstract_class = true
   end
```
5. Add the validations i.e.
```
  it { should validate_presence_of(:title) }
  it { should validate_presence_of(:body) }
```
6. Add the relationships i.e.
```
  it { should belong_to :a_different_model_object }
```

## Migration
1. if we get this error:
* `/Users/aleneschlereth/turing/1711/practice/blogger/db/schema.rb doesn't exist yet.`
* `ActiveRecord::NoDatabaseError:
FATAL: database "something" does not exist` - run `rails db:created` to create the test/devo databases
* `ActiveRecord::StatementInvalid:
PG::UnidentifinedTable: ERROR: relation "songs" does not exist` - we have to create a migration
2. `rails generate migration CreateObjects title:string body:text` - Run this, the Create[feature/model] and add the rows/columns you need, in the set list example we had title:string, length:integer, and play_count:integer. You can set defaults here after the `t.string :status, default: "New"`
3. open that migration file you created and in the create method add a timestamp! `t.timestamps`
4. `rake db:migrate` - because the rails g migration is only a set of instructions, this will actually "create the table"
5. `bin/rails db:migrate RAILS_ENV=test` OR `bin/rake db:migrate` - based on what the error tells you to do
6. go to` db/schema.rb` this is what our current structure of our database looks like.
7. Use active_designer to make it more visual `active_designer --create db/schema.rb` You'll notice that this has added an active_designer directory with an index.html in it. This has been built off your schema.rb. When you run the command `open active_designer/index.html` a web page will open up with a visual depiction of the current structure of your database.

## Rails console
5. Use `rails console` or `rails c` to allows you to access and work with just about any part of your application directly instead of going through the web interface. This allows you to add stuff to your devo database. You can use this like IRB. You can add things to the database this way. i.e.
```$ object = Object.new
   $ object.title = "Sample Object Title"
   $ object.body = "This is the text for my object, woo hoo!"
   $ object.save
   $ Object.all
```
You have to save the changes you made!


## Git workflow expample
- follow typical add/commit process
- create new branches for every feature/functionality
- commit & merge and make a pull request with a PR with your changes for example:
```
Add Object Model
* Add Spec with validations for title and body
* Add migration to create objects table in DB
* Add Object model
* Add validations for title and body to Object model
* Test is passing
```
- delete branches after!

## Setting up the Router
- Errors! No routes matching whatever! Typically you can use those routes mentioned. After a link or a button, you can use `method: :get`, `method: :update`, `method: :delete`, `method: :patch`, `method: :put` to help with the routes.
```
ActionController::RoutingError:
    No route matches [GET] "/objects"
```
- add `resources :objects` to routes.rb. This line tells Rails that we have a resource named objects and the router. This will give
```      
    Prefix Verb   URI Pattern                  Controller#Action
    objects GET    /objects(.:format)          objects#index
             POST   /objects(.:format)          objects#create
 new_object GET    /objects/new(.:format)      objects#new
edit_object GET    /objects/:id/edit(.:format) objects#edit
     object GET    /objects/:id(.:format)      objects#show
             PATCH  /objects/:id(.:format)      objects#update
             PUT    /objects/:id(.:format)      objects#update
             DELETE /objects/:id(.:format)      objects#destroy
```
These are the seven core actions of Rails' REST implementation. If you comment out the `resources :objects` it will say that there are no routes created.
- to be RESTful, you typically want to be able to utilize these, so seperate objects/models should have their own controllers to route to.

## Creating the Controller
1. We should be getting this error
```
ActionController::RoutingError:
    uninitialized constant ObjectsController
```
2. `touch app/controllers/objects_controller.rb`
3. Add
```class ObjectsController < ApplicationController
end
```
to the objects controller file.
4. now we should be getting an error that there is no action 'index' we can add this method by adding 
```def index
  @objects = Object.all
end
```
Need to utilize the built in methods!

Things to do for travis and heroku configurations:
- bundle install with figaro
- add api keys to application.yml file
- travis setup heroku
- travis encrypt $(heroku auth:token) --add deploy.api_key
- travis encrypt MY_SECRET_ENV=super_secret --add env.global
- figaro heroku:set -e production
- rake figaro:heroku
