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

Install RVM
-----------------------------

In your rails sample app's Cloud9 project workspace, open a Terminal window.
Run::

  curl -L https://get.rvm.io | bash -s stable

Once that command finishes, you will need to close your terminal window, and 
then open it back up, in order to reload the source of the rvm command in your 
Cloud9 teminal. 

In your new Terminal window, run the following command to check that RVM is 
working, and also choose a ruby version to use in this project::

  rvm install 1.9.3

Install Gems
-----------------------------

In your Cloud9 Terminal, run this command to create a name for the rvm gemset 
that you'll be using for this project::

  rvm use --create 1.9.3@rails_sample_app

Run the bundle install command to install all of the gems in your Gemfile::

  bundle install

Run the rails app in Cloud9
-----------------------------

In your rails sample app's Cloud9 Terminal window, run::

  rails s -b $IP -p $PORT

That's it! Your rails app will now be running. You can view your running rails 
app at ``https://__project-name__.__username__.c9.io``.

.. note:: Use your cloud9 own username and project name in the URL to view your
   app.

