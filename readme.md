# Description

EmeraldBox is a boilerplate framework for developing python web applications with database access. 
The underlying web framework is Flask, a python microframework based on werkzeug, jinja2 and good intentions. 
Flask gives a quite complete basic package. EmeraldBox gives structure and helper tools to speed up development and app deployment on servers.
Several basic packages commonly used in developing web applications are included.

Since EmeraldBox is derived from Flask, it uses a lot of Flask patterns and also provides a structure to Flask applications based on Flask's best practice for large applications. However, EmeraldBox did not implement Blueprint.

The structure implemented is mostly based on the following links:
* http://blog.miguelgrinberg.com/post/the-flask-mega-tutorial-part-i-hello-world by Miguel Grinberg
* http://flask.pocoo.org/docs/patterns/packages/ by Armin Ronacher

# Motivation
Developing web apps should be done in the easiest and most efficient ways. Python offers that. 
However, most of the available frameworks required a deep learning curve for new users and most users have problems deploying the web app. 

After using several python web frameworks as well as using other languages' frameworks like Rails, CodeIgniter and Zend, the author came to a conclusion that python is the easiest and most efficient language. 

However, it will require tools that may speed up development. It that sense, Rails has a very good approach. 
Integration with 3rd party packages should also comes easily without having the need to interfere with the main OS. 

Thus, comes EmeraldBox, an easy-to-use, light-weight, and easy-to-deploy framework.

EmeraldBox comes in a localized environment using the well-known virtualenv and includes standard packages that are commonly used in web development. The tool includes data management tools based on SQLAlchemy and is designed to give ease for developers in managing database and migrations. A more rails-like approach is used since it helps developers in many ways.

# Installer package

To run EmeraldBox, you need python 2.5 and above. However, Python 3 is not yet supported.

EmeraldBox setup will install the following packages for you:
* Flask
* Flask-Mail
* Flask-SQLAlchemy
* SQLAlchemy
* SQLAlchemy-Migrate
* Nose
* Tornado Web Server

You can add your desired python package by running:

    box/bin/pip install <package name>

# Setup

clone repository

    git clone https://github.com/femmerling/EmeraldBox.git <project_name>

EmeraldBox is a localized environment build using virtualenv.
To adjust the environment settings to your local environment, go to the root EmeraldBox directory and run:

    python setup.py

The setup will then automatically download packages and adjusted your settings.

If you want to control your project using git do the followings:

change to directory of <project_name>

    cd <project_name>

add replace remote

    git remote rm origin
    git remote add origin <new_remote like git@github.com:your_name/project_name.git>
    git commit -am "initial setup"
    git push origin master

# Server and Deployment

As all python frameworks, EmeraldBox is dependent on WSGI. Worry not! EmeraldBox comes with the famous Tornado Web Server. 
Tornado is integrated for 4 reasons:
* The integration with Flask is straightforward.
* It has a good WSGI wrapper.
* It is highly scalable.
* It is secure.

You EmeraldBox package is a ready to deploy package and your app is ready to be published since instalation. Run the server using:
        
    ./ignite.py

The app will run at port 5000. You can change the port in the ignite.py file to any port you wish for. Just make sure that the port is available and does not conflict with other services.

# Usage

Framework generators and tools available. to see the functions run:

    ./box.py -h

Automated database creation tool available.

Run the following:

    ./box.py -n <Model Name> <field name>:<field type>--<field length (optional)>

This will create an automated data management tool for Create, Read, Update and Delete.
You can access the tool at <server_root>/<model name in lowercase>

Your database will then be migrated and EmeraldBox will automatically create the tables in the database. This also creates a controller in your controller file for handling the JSON output of your model.
Check app/main.py to see the result.

If you have your code and want to deploy it elsewhere, you can get the same database scheme automatically in the new server by running the database creation and migration tool.

Simply run:

    ./box.py -c

And your database will be created. Afterwards, run:

    ./box.py -m

This will migrate your database to the latest version and making it ready for use with your code.


You can also initiate your own controller in the controller file.
Simply run the following

    ./box.py -i <controller name>

this controller initiation will also automatically generate a view file in your app/templates/ folder with your controller name as the file name.

# Testing

Currently we include Nosetest into the package. You can use it to perform BDD.

To execute Nose, simply run the following

    box/bin/nosetests

# Other Notes

Currently this is the only documentation available and the project is still developing from day to day. Use carefully!

If you wish to use a rather stable version, use download the package from http://emeraldbox.emfeld.com.

Currently the package is tested only on unix/linux systems. No support is currently provided for Windows (sorry windows fans).

for documentation on python see http://www.python.org <br>
for documentation on Flask see http://flask.pocoo.org <br>
for documentation on SQLAlchemy see http://www.sqlalchemy.org <br>

# Contributing

If you found any issues please put them in the issue section.

To contribute, simply place a pull request and email the author at erich@emfeld.com

# Ending Note

This framework adds the diversity in python, a language which have more web frameworks than keywords.
Thank you for trying it out and all suggestions are welcome.