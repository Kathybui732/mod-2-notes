* `app` - This is where 98% of your effort will go. It contains subfolders which will hold most of the code you write including Models, Controllers, Views, Helpers, JavaScript, etc.
* `bin` - This is where your app's executables are stored: `bundle`, `rails`, `rake`, `spring`, and, something a lot of people are excited about for Rails 5, `yarn`.
* `config` - Control the environment settings for your application. It also includes the `initializers` subfolder which holds items to be run on startup.
* `db` - Will eventually have a `migrations` subfolder where your migrations, used to structure the database, will be stored. When using SQLite3, as is the Rails default, the database file will also be stored in this folder.
* `lib` - This folder is to store code you control that is reusable outside the project.
* `log` - Log files, one for each environment (development, test, production)
* `public` - Static files can be stored and accessed from here, but all the interesting things (JavaScript, Images, CSS) have been moved up to `app` since Rails 3.1
* `spec` - When you install RSpec, it creates this directory as well as a `rails_helper.rb` and a `spec_helper.rb` file. Your tests will live here. You probably don't see this folder right now, but we'll circle back around to installing RSpec.
* `tmp` - Temporary cached files
* `vendor` - Infrequently used, this folder is to store code you *do not* control. With Bundler and Rubygems, we generally don't need anything in here during development.
