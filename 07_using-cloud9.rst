.. _use_cloud9:

#############################
 Using Cloud9
#############################

Cloud9 is a virtual Linux development environment for projects. Project code 
is hosted on a remote repository at either GitHub or BitBucket, and a working 
copy of a project repository will be cloned into the Cloud9 development space. 

Clone a Remote Project
=============================

+ Login to your Cloud9 session at https://c9.io/
+ Under :menuselection:`PROJECTS ON GITHUB`, click a project name

  .. image:: _images/07_cloud9-1.png

+ Click button :guilabel:`CLONE TO EDIT` 
+ Click button :guilabel:`CREATE` to create a workspace in :menuselection:`MY PROJECTS`

  .. image:: _images/07_cloud9-2.png

+ Click button :guilabel:`START EDITING`; the Cloud9 edit space will display
+ Double-click a document name in the left-hand file list to edit the document

Git and GitHub Integration
=============================

The clever developers at Cloud9 have integrated many functions into the 
workspace menu. For example, Git functionss can be run from there:

  .. image:: _images/07_cloud9-3.png

Missing from the Git menu selections is the ``git add .`` command. Fortunately
there is an embedded command line at the bottom of the Cloud9 workspace. 