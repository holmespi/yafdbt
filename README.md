ya
<pre>
===================
||   ______      ||
||  /\  *  \     ||
||  \ \   __\    ||
||   \ \ \__/    ||
||    \ \ \      ||
||     \ \_\ AUL ||
||      \/_/     ||
||               ||
===================
</pre>

PAUL'S BIG TUTORIAL
===================

DJAGNO ULTIMATE FREE PHOTO BLOG TUTORIAL WITH INSTRUCTIONS FOR HOSTING
---------------------------------------------------------------

What alot of these Django Tutorials don't tell you is that once you build your nice blog or app your biggest trouble will be finding good hosting  that supports Django.

Even after you find the hosting, you're probably going to run into some issues your first time deploying a site or web app.  That is why this tutorial goes into detail on how to set up your project to deploy easily on Heroku.  Heroku can not support media uploads, however, because of its 'ephemeral filesystem.'  So the lesson also shows how to automatically push your uploads to  Amazon Simple Storage Service (S3).

Best of all, these sites (Heroku and S3), offer free tiers. As long as you aren't getting more than around 10 hits a minute, you are probably covered.

I also show how to get a free TLD from freenom.com and hook that up to your heroku site.




REQUIREMENTS
------------
* PYTHON
* X-CODE (DEVELOPER TOOLS)
* PIP
* HOMEBREW
* GIT
* DJANGO
* GUNICORN
* PSYCOPG2
* BOTO
* DJANGO-STORAGES
* DJANGO-TOOLBELT
* AMAZON S3 ACCOUNT
* HEROKU ACCOUNT





HOW TO INSTALL STUFF
-------------------


* #### X-CODE
    1. go to the apple website and download and install x-code, if it is not already installed on your system.


* ####  PIP
	1. get: [pip.py](https://raw.github.com/pypa/pip/master/contrib/get-pip.py)
	2. save as get-pip.py
	3. open terminal
	4. in terminal change into the directory that holds get-pip.py
	5. type:

            python get-pip.py

* ####  HOMEBREW
	1. in terminal type:

                ruby -e "$(curl -fsSL https://raw.github.com/mxcl/homebrew/go/install)"

* ####  GIT
	1. in terminal type:

            brew install git

* ####  DJANGO
	1. in terminal type:

            sudo pip install django==1.5.4

* ####  GUNICORN (needed for heroku)
	1. in terminal enter

            pip install gunicorn

* ####  PSYCOPG2 (needed for heroku)
	1. In terminal enter:

            pip install psycopg2

* ####  HEROKU-TOOLBELT
    1. Get the [heroku toolbelt](https://toolbelt.heroku.com/)
	and install!

* ####  BOTO (needed for amazon s3)
	1. in terminal enter:

            pip install boto

* ####  DJANGO-STORAGES (needed for amazon s3)
	1. In terminal enter:

        	pip install django-storages

	
	




GETTINGS STARTED
----------------
	
### Part One: Setting up our Projects Structure

We'll need to **initialize a Django Project**.  This is done with terminal.  Let's call our project `yolo_x_kanye`.  So in terminal type:
        
        django-admin.py startproject yolo_x_kanye


This creates a folder containing neccessary files for starting our project.  This directory is structured like so:
    
        \yolo_x_kanye
            -manage.py
            \yolo_x_kanye
                -settings.py
                -wsgi.py
                -urls.py

Next we need to **start an app**, we will be building a simple blog.  Starting a django app creates the files needed to build your Models, Views, and Controllers (MVC).  I've found the best way to understand a MVC framework is through building a project.  

To start an app with Django we use the `manage.py` file.  We will call our app 'holy_grail'.  So... with terminal change into project directory's root (the directory with manage.py file) and type:

		./manage.py startapp holy_grail
		
Now if we look at the structure of our project we have something like this:

        \yolo_x_kanye
            -manage.py
            \yolo_x_kanye
                -settings.py
                -wsgi.py
                -urls.py
            \holy_grail
                -__init__.py
                -models.py
                -tests.py
                -views.py
                
Don't worry about these new files for right now, we will learn what they do was we build the project.

The next step I usually take is creating folders to store things like static files (such as CSS, Javascript, Images), templates (the html files that our website will use), media uploads (for us, images associated with each blog post).

In our projects root directory create a folder called `static`, a folder called `templates`, and a folder called `media`.

### Part Two: Building the Settings
We are going to be editing the settings.py file now.  
 -bring in paths variables snippet
 -sqlite3 for database, give db a name
 -put static_path variable in static dirs
 -put media_path variable in media url, set media root /media/
-enable admin
-add app
		
		setup some urls
		-remember the dev. media server and import settings
		
		setup models.py
		-one for photos
		-one for posts
		
		setup admin.py
		-from django.contrib import admin

		start a git repo
		-git init
		-git add -a
		-git commit -am "init"
		
		sync the database
		-./manage.py syncdb
		
		create template files
		-use file browser or:
		 -cd to templates
		 -touch base.html blog.html

		setup urls
		-import views
		-url to templates
		
		setup views
		-import models
		
		write templates
		-base
		-blog
		-about

		test site locally
		
		git commit
		-git commit -am "<some-commit-message>"
	
	******************
	***SETUP HEROKU***
	
		create procfile
		-cd to root of project
		-web: gunicorn <project-name>.wsgi
		
		create requirements.txt 
		-pip freeze > requirements.txt
		
		heroku create
		
		browse to heroku and get the database info
		enter this into settings

		push to heroku
		-git status to see what needs to be added
		-git add .
		-git commit -am "settings for heroku"

		sync database on heroku
		-heroku run python manage.py syncdb
		-setup the admin

		scale heroku dynos to :1
		-heroku ps:scale web=1
	
	**************
	***SETUP S3***
	
		create bucket
		
		create bucket policy and cors config
		
		find your secret keys
		
		setup settings for s3
		(media and static urls)
	
	
	
	
	

==============================
PUBLISHED IN THE PUBLIC DOMAIN
==============================
