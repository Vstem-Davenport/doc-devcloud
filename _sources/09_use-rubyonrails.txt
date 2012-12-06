.. _use_rubyonrails:

#############################
 Ruby on Rails Sample App
############################# 

Sample Rails App 
=============================

Rails is the most popular framework for doing web applications with ruby.
Many popular web applications such as Twitter, Hulu, and Github are written in 
Ruby on Rails. Running a simple RoR web app for development testing is 
relatively quick and easy in the Cloud9 environment.

Get a sample rails app
-----------------------------

#. First, fork a sample rails application on GitHub. Go to:

   https://github.com/vstem-davenport/sample_app

   ...and click the :guilabel:`fork` button.

   GitHub will create a copy of the project on your account.

#. Next, open your Cloud9 dashboard. Select menu item :menuselection:`Projects 
   On Github --> Sample app` on the left sidebar. 
#. Then click button :guilabel:`Clone to Edit` to clone a copy of the project in 
   your Cloud9 virtual workstation.
#. Once the project is finished cloning to Cloud9, open the project workspace by 
   clicking the :guilabel:`Start Editing` button.

Install Ruby
-----------------------------

Ruby is installed using :program:`RVM`, the Ruby Version Manager. Cloud9 
provides a pre-installed emulation of RVM, which we will use.

Open a terminal window in the rails sample app's Cloud9 project workspace.
In the Terminal window, run the following command to check that RVM is 
working, and also choose a ruby version to use in this project::

  rvm use 1.9.3

Install Gems
-----------------------------

Run the command :command:`bundle install` to install all ruby gems from the 
project in your Gemfile::

  bundle install

Set up the database
-----------------------------

Use the :command:`rake` (Ruby make) command to set up the development database 
structure::

  rake db:migrate

Test run app in Cloud9
-----------------------------

In the rails sample app's Cloud9 Terminal window, run::

  rails s -b $IP -p $PORT

Your app will be running now, served locally for testing. View the running rails 
app at :file:`http://__project-name__.__username__.c9.io`.

.. note:: Use your own cloud9 username and project name in the URL to view your
   app.

-----------

.. _use_heroku:

#############################
 Using Heroku
#############################

When an application is ready for release, Heroku provides a public web 
application deployment service for free. Heroku integrates with the Cloud9
development environment and GitHub repositories using Git commands. Following is 
a brief outline for configuring and deploying a project on Heroku.

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

+ At the console command line, type::
  
    heroku create
  
  This creates a heroku server for the app, and configures a remote location
  in git. Pushing the repository to the remote location will deploy the app.

+ To see the new git heroku deployment branch, type::

    git remote -v

+ Open a new browser tab, and bookmark the url of your new heroku server, which 
  is displayed in the output of the :command:`heroku create` command. The URL 
  will look similar to this:: 

    random-word-1234.herokuapp.com

+ After making changes to the project in Cloud9 and pushing to the GitHub 
  repository, deploy changes on Heroku with the additional command::

    git push heroku master

+ Now the live site can be viewed across the Internet at the heroku server URL
  which you bookmarked earlier.

