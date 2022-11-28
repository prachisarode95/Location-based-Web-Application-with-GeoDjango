
# Development of Location-based Web Application using GeoDjango framework.

## Introduction

This project is about building a simple nearby shops application that lists the shops closest to a user’s location.
 
I used Django framework to build a web application from scratch. 'GeoDjango' is the sub-framework used to implement geolocation features in the application. Also used a spatial database, PostgreSQL and its extension PostGIS, to get benefits from the spatial features and implement location-aware web apps.

## Tools Used

    1. The Python programming language
    2. The Django web framework
    3. The PostgreSQL database for persisting data
    4. The PostGIS extension for supporting spatial features in the PostgreSQL database
    5. pip for installing dependencies
    6. The 'venv' module for managing a virtual environment
    7. Docker for installing PostgreSQL and PostGIS
## Geospatial Libraries Used

These libraries were installed on windows 10 system.

    1. GEOS
    2. GDAL
    3. PROJ.4
    4. GeoIP 



## Flow of Development

### Creating a Virtual Environment

A virtual environment allows you to create an isolated environment for the dependencies of the project. This allows you to avoid conflicts between the same packages that have different versions.

### Install Django

The first step after creating and activating a virtual environment is to install Django. 

### Creating a Django Project

This project is a web application that lists shops sorted by distance so your users will be able to discover the shops that are close to their location.

The web application makes use of GeoDjango for easily implementing location requirements like calculating the distances of shops from the user’s location and ordering the shops by distance.

Using GeoDjango, you can get and display the nearest shops that are stored in a PostgreSQL database configured with the PostGIS extension to enable spatial operations.

### Configuring the PostgreSQL Database

Configure the connection to the PostgreSQL and PostGIS spatial database using docker facility for a quick setup.

### Adding GeoDjango

GeoDjango is a framework that makes it as easy as possible to build GIS and location aware web applications. It can be added by simply including the 'gis contrib' module in the list of installed apps.

### Creating a Django Application

A Django project is made up of many applications. By default, it contains several core or built-in apps like django.contrib.admin, but I added one app that contains the custom project’s code.
The next step is to create a Django application that may call shops.

The shops application contains the code for creating and displaying the shops closest to a user’s location. Following are the tasks to be performed:

    1. Create the app
    2. Add a Shop model
    3. Add a data migration for loading initial demo data (shops)
    4. Add a view function
    5. Add a template

### Creating a Django Model

After creating the shops application, which contains the actual code of the project, it's time to add models in the app. Django uses an ORM (Object Relational Mapper), which is an abstraction layer between Django and the database that transforms Python objects (or models) into database tables.

In this case, you need one model that represents a shop in the database. So, I created a Shop model that has the following fields:

    1. name: the name of the shop.
    2. location: the location of the shop in latitude and longitude coordinates.
    3. address: the address of the shop.
    4. city: the city the shop is in.

### Creating the Database Tables

With Django, there is no need to use SQL to create the database tables thanks to its ORM.

### Adding a Super User

I created a super user to access the admin interface.

### Registering the Model in the Admin Interface

Django’s admin application provides a complete CRUD interface for managing data.

GeoDjango extends the admin application to add support for working with geometry fields.

Before you can access your models from Django admin, you need to register them.

### Adding Initial Data

You need some data for your application, but instead of manually adding it, I used a data migration method.

Data migrations can be used for multiple scenarios, including adding initial data in the database.

Before creating a migration, I got some real-world data from OpenStreetMap using overpass turbo, a web-based data filtering tool for OpenStreetMap.

### Adding logics to the scripts

After running the application now, the data from the 'data.json' file will be loaded in the database table.
By running the Django application server and heading to the admin interface. You will see the data in the table on the web screen.

### Displaying Nearby Shops

The 'Shops' application, which encapsulates the code for creating and getting nearby shops in project.
Now the application is ready to run on its Django server. The home page will display just a simple un-styled list with the nearest shops from the pre-defined user’s location.
## Conclusion

This is a location based web application built using GeoDjango, which aims to become a world-class geographic framework for implementing GIS apps. 
Nowadays, location aware apps (apps that know your location and help you discover nearby objects and services by offering you results based on your location) 
are all the rage. Using the knowledge I gained while building this application, I was able to incorporate this modern feature in the application.

The only requirement, besides the dependencies of GeoDjango, is to use a spatial database (a database that’s capable of storing and manipulating spatial data). 
For PostgreSQL, one of the most popular database management systems used with Django, you can simply install the PostGIS extension with your database to turn it into a spatial database. 
Other popular databases like Oracle and MySQL have built-in support for spatial data.