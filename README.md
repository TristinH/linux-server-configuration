# Linux Server Configuration

## IP and URL
IP Address: 34.195.89.57

URL: http://34.195.89.57/

## Software Installed, Configurations, and Third Party Resources

### Apache
To serve my python application, I installed Apache 2. This allowed my to easily set up my app to run on my AWS instance. 

#### Configuration
I had to configure Apache to run WSGI applications by moving my app to the /var/www directory and creating a .wsgi script in the
same directory to ensure the app ran correctly. To notify Apache of the app I created a .conf file for the app in the 
/etc/apache2/sites-available directory giving Apache the necessary information to run the app.  

#### Resources
The main resource I used to properly install and configure apache was a how to guide at this [link](https://www.digitalocean.com/community/tutorials/how-to-deploy-a-flask-application-on-an-ubuntu-vps). It provided a step by
step process to aid you in allowing Apache to successfully serve your app on your instance. 


### UFW
UFW is the default firewall that comes with the standard Ubuntu installations. I set up the firewall to only allow particular incoming 
connections to improve my app's security

#### Configuration
I configured UFW to default to deny all incoming connections. The exceptions to this are SSH on port 2200, HTTP on port 80, and NTP on 
port 123. Attempts to connect via any other ports will not be successful. 

#### Resources
To troubleshoot issues I had with UFW I frequented the Ubuntu community help page for UFW at this [link](https://help.ubuntu.com/community/UFW).


### Flask
Flask is a Python framework for developing web applications. It allows for ease in web development through its simple URL routing, 
support for HTML templating, and more. This was the main component for the application to run successfully.

#### Configuration
The default installation of Flask was sufficient to run the application as developed. All that was required was to install Flask using 
the pip command which abstracts a lot of the installation and setup. 

#### Resources
To learn how to install Flask, I followed the instructions given on the Flask [website](http://flask.pocoo.org/).


### PostgreSQL
PostgreSQL is a database system used in many database driven applications. It is used to create and maintain the databases that serve
your application. It provides exceptional functionality and the ability to setup databases with ease

#### Configuration
I used apt-get to perform the base installation for PostgreSQL. From there I had to login to the database to make the configurations to 
allow my app to use its databases. The first change I made was a security change. I configured PostgreSQL to not allow any remote 
connections. After that I proceeded to setup the database for the application. First I set up a user named 'catalog' with limited 
permissions for the application. I then created a database owned by this user that it would use for the application. After I set up the 
user and the database, I used SQL Alchemy to configure the database properly to use in my application. More on SQL Alchemy below.

#### Resources
A lot of information for how to install and use PostgreSQL can be found on this [website](https://www.postgresql.org/). Additionally, 
to ensure the database was set up securely I followed this [guide](https://www.digitalocean.com/community/tutorials/how-to-secure-postgresql-on-an-ubuntu-vps).


### SQL Alchemy
SQL Alchemy is an object relational mapper that simplifies a lot of the hassle of setting up a database driven application. It makes
it possible to structure your code in a way that takes advantage of object oriented programming aspects with a database backing it.

#### Configuration
The default installation of SQL Alchemy was sufficient to successfully run my application. 

#### Resources
The SQL Alchemy [website](https://www.sqlalchemy.org/) provided all that was necessary to properly install and set up SQL Alchemy for
use in an application. 


### Git
Git is a popular version control system for source code management. It allows developers to keep track of changes in their code and
develop in a way that ensures that bugs can be dealt with easily. Git was used to obtain the source code for the application which was
developed for a previous [Udacity project](https://github.com/TristinH/item-catalog).

#### Configuration
Git was installed by default on my AWS instance. Therefore, no special configuration was required on my part

#### Resources
To learn how to clone and perform other useful actions I referenced this [link](https://git-scm.com/).
