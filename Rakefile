# rake -T Lists available rake tasks and their description
# For the command to work add a desc before task definition
# Namespacing Rake Tasks - a way to group or contain something in this case Rake tasks
# bundle exec rake ie rake aborted : coomon with issue/error with rake.
#!FIX Prepend bundle exec infront of your rake command

namespace :greeting do
desc 'outputs hello to the terminal'
  task :hello do
    puts "hello from Rake!"
  end

  desc 'outputs hola to the terminal'
  task :hola do
    puts "hola de Rake!"
  end
end

namespace :db do
  desc 'migrate changes to your database'
  task migrate: :environment do # creates task dependency ie wants access to env.rb
    Student.create_table
  end

  desc 'seed the database with some dummy data'
  task seed: :environment do
    require_relative './db/seeds'
  end
end

# Create the environment tasks and run bundle exec rake db:migrate
task :environment do
  require_relative './config/environment'
end

desc 'drop into the Pry console'
task console: :environment do
  Pry.start
end