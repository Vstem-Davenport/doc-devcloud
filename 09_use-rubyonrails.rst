.. _use_rubyonrails:

#############################
 Ruby on Rails Sample App
############################# 

Sample Rails App 
=============================

Rails is the most popular framework for doing web applications with ruby.
Many popular web applications such as Twitter, Hulu, and Github are written in 
Ruby on Rails.
Getting a simple web app up and running on RoR is relatively quick
and easy. 


Get a sample rails app
-----------------------------

First, fork your rails sample app on GitHub. Go to:

https://github.com/vstem-davenport/sample_app

...and click the :guilabel:`fork` button.

Now you have a copy of the project on your Github account.

Next, go to your Cloud9 dashboard and click on the project name under "Projects
On Github" in the left sidebar. Then click the :guilabel:`Clone to Edit` button 
to clone a copy of the project to your Cloud9 virtual workstation.

Once your project is finished cloning to Cloud9, open the project workspace by 
clicking the :guilabel:`Start Editing` button.

Install Ruby
-----------------------------

Ruby is installed using RVM, the Ruby Version Manager. In Cloud9, RVM is already
pre-installed, so all you have to do is use it.

In your rails sample app's Cloud9 project workspace, open a Terminal window.
In your new Terminal window, run the following command to check that RVM is 
working, and also choose a ruby version to use in this project::

  rvm use 1.9.3

Install Gems
-----------------------------

Run the bundle install command to install all of the gems in your Gemfile::

  bundle install

Set up the Database
----------------------------

Use the rake (Ruby make) command to set up your development database structure::

  rake db:migrate

Run the rails app in Cloud9
-----------------------------

In your rails sample app's Cloud9 Terminal window, run::

  rails s -b $IP -p $PORT

That's it! Your rails app will now be running. You can view your running rails 
app at ``http://__project-name__.__username__.c9.io``.

.. note:: Use your cloud9 own username and project name in the URL to view your
   app.

-----------

.. _use_heroku:

#############################
 Using Heroku
#############################

Heroku provides a free web application deployment services, integrated with 
the Cloud9 development environment through Git and GitHub. Following is a 
brief outline for configuring and deploying a project on Heroku.

Install Heroku Tools
=============================
+ Open a project in Cloud9
+ In the Cloud9 Project, choose :menuselection:`View --> Console` from the menu
+ At the console command line, type::
  
    c9pm install heroku

+ To make sure that your install was successful, and to get ready to use heroku,
  run the following command in your Terminal::
    
    heroku login
  
  Enter your heroku username and password when prompted.

Add Heroku Server to Project
=============================

+ Open a project in Cloud9
+ In the Cloud9 Project, choose :menuselection:`View --> Console` from the menu
+ At the console command line, type::
  
    heroku create
  
  This will create a heroku server for your app, and configure your git 
  repository with an extra remote location that you can push to to deploy your 
  app.

+ To see the new git heroku deployment branch, type::

    git remote -v

+ Open in a new browser tab, and bookmark, the url of your new heroku server,
  which you will see in the output of the ``heroku create`` command. The URL 
  will look similar to this:: 

    random-word-1234.herokuapp.com

+ After making changes to the project in Cloud9 and pushing to the GitHub 
  repository, deploy changes on Heroku with the additional command::

    git push heroku master

+ Now you can view your live site at your heroku server URL (which you 
  bookmarked earlier).

