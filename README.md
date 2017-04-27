# Linux Server Configuration

## IP and URL
IP Address: 34.195.89.57

URL: http://34.195.89.57/

## Software Installed, Configurations, and Third Party Resources

### Apache
To serve my python application, I installed Apache 2. This allowed my to easily set up my app to run on my AWS instance. 

#### Configurations
I had to configure Apache to run WSGI applications by moving my app to the /var/www directory and creating a .wsgi script in the
same directory to ensure the app ran correctly. To notify Apache of the app I created a .conf file for the app in the 
/etc/apache2/sites-available directory giving Apache the necessary information to run the app.  

#### Resources
The main resource I used to properly install and configure apache was a how to guide at this [link](https://www.digitalocean.com/community/tutorials/how-to-deploy-a-flask-application-on-an-ubuntu-vps).
