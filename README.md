# Linux Server Config

# Description
Serves the Item Catalog Flask App previously created and hosts it on an Amazon Lightsail virtual machine running Ubuntu.
The Oauth login does not work in current state, I have left it that way due to viewing the knowledge discussions and seeing the post stating that getting oauth login to work on this project is not necessary.

The website is accessible through the public IP and serves the main catalog page of the Flask app. It connect to the database and is able to navigate to any page that does not require login. (Due to the oauth issue)


# Functionality

Public IP: 54.224.188.235
SSH PORT: 2200
URL: 54.224.188.235  (I did not see a requirement to DNS, and xip.io was down when I tried to add it, so I left as the IP.)

Firewall is set to limit access to ports 2200, 80, 123. 

There is a grader user, provided on the VM with SUDO access.
USER: grader
Password login is denied, but a private key is sent to grader.


# Resources
I used this site, http://terokarvinen.com/2016/deploy-flask-python3-on-apache2-ubuntu#comment-7694 to help with the Flask and apache setup on Ubuntu. It wouldn't work until i manipulated the .conf file like expressed on that doc.

Several Stack overflow articles were viewed in the troubleshooting of configuring the VM.

Flask Documentation and several digital ocean articles also helped explain the deployment process, as well as the Udacity videos and knowledge support questions. 


# Software and Changes to the VM

Installed on the Ubuntu VM:
flask-sqlalchemy, python3, pip3, postgresql, psycopg2, flask, oauth2client, libapache2-mod-wsgi-py3, git.

Created a database, itemCat, and ran database_setup.py and add_itesm.py.
The database gets accessed through a db user 'catalog', which has limited access.

Configured time to UTC

