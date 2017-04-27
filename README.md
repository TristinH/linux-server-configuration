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
The main resource I used to properly install and configure apache was a how to guide at this [link](https://www.digitalocean.com/community/tutorials/how-to-deploy-a-flask-application-on-an-ubuntu-vps). It provided a step by
step process to aid you in allowing Apache to successfully serve your app on your instance. 


### UFW
UFW is the default firewall that comes with the standard Ubuntu installations. I set up the firewall to only allow particular incoming 
connections to improve my app's security

#### Configurations
I configured UFW to default to deny all incoming connections. The exceptions to this are SSH on port 2200, HTTP on port 80, and NTP on 
port 123. Attempts to connect via any other ports will not be successful. 

#### Resources
To troubleshoot issues I had with UFW I frequented the Ubuntu community help page for UFW at this [link](https://help.ubuntu.com/community/UFW).


### Flask

