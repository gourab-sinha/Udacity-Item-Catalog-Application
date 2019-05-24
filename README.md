# Udacity Item Catalog Application
Item Catalog Application is the second project of Udacity Full Stack Web Development Nano Degree Program.
# Application Summary
The goal of this application or project is to deploy skills of full stack web development such as RESTFul web application that uses python Flask framework with Oauth authentication. CRUD implementaion to provide support of create, view, update and delete. This application works on local environment.
# Software Requirements
This application runs on local environment.
All required software to run this application is already made available in Vagrantfile provided by Udacity. Hence separately no installation is required.
Application:
1. [Python - 3.5](https://www.python.org/download/releases/3.0/)
2. [Vagrant - 2.2.4](https://releases.hashicorp.com/vagrant/2.2.4/vagrant_2.2.4_x86_64.msi)
3. [Virtualbox - 6.0.4](https://download.virtualbox.org/virtualbox/6.0.4/VirtualBox-6.0.4-128413-Win.exe)
4. [Git - 2.21.0.windows.1](https://git-scm.com/download/win)
# How to run the project
A. Download(Optional):
1. [Git](https://git-scm.com/download/win)
2. [Virtual Box](https://download.virtualbox.org/virtualbox/6.0.4/VirtualBox-6.0.4-128413-Win.exe)
3. [Vagrant](https://releases.hashicorp.com/vagrant/2.2.4/vagrant_2.2.4_x86_64.msi)
4. [Vagrantfile](https://s3.amazonaws.com/video.udacity-data.com/topher/2019/March/5c7ebe7a_vagrant-configuration-windows/vagrant-configuration-windows.zip)

B. Installation(If not installed):
1. Git
2. Virtual Box
3. Vagrant

C. Run
1. Open command prompt or gitbash terminal
2. Create new directory or you can use existing one. For creating directory use mkdir 'DirectoryName' on gitbash terminal/cmd.
3. Goto the directory where you want to keep your files and paste downloaded Vagrantfile inside the folder.
4. Open VirtualBox
5. 'vagrant up' on gitbash/cmd in that folder.
6. 'vagrant ssh' on gitbash/cmd once step 5th successfully completed.
7. Run 'cd /vagrant' on gitbash/cmd to goto shared directory between host and guest machine.
8. clone repository in the shared directory or you can create one and clone inside the folder.
9. After completing step 8th, on vagrant goto that folder where repository cloned and run 'python3 database_setup.py'
10. To populate database run 'python3 lotsofmenus.py'
11. Now run 'python3 application.py', it will start the server.
12. Now open browser and type 'https://localhost:5000/' in URL bar to see homepage.

# Navigation in application
1. 'https://localhost:5000/' or 'https://localhost:5000/restaurant/' to view the homepage.
2. 'https://localhost:5000/restaurant/new/' to add new restaurant in database.(Required login)
3. 'https://localhost:5000/restaurant/<int:restaurant_id>/edit/' to edit restaurant name(Required login and permission)
4. 'https://localhost:5000/restaurant/<int:restaurant_id>/delete/' to delete restaurant from database.(Required login and permission)
5. 'https://localhost:5000/restaurant/<int:restaurant_id>/menu/' or 'https://localhost:5000/restaurant/<int:restaurant_id>/' to view all the items available in the restaurant.
6. 'https://localhost:5000/restaurant/<int:restaurant_id>/menu/new/' to add menu item for a restaurant.(Required login)
7. 'https://localhost:5000/restaurant/<int:restaurant_id>/menu/<int:menu_id>/edit'to edit menu item of a restaurant.(Required login and permission)
8. 'https://localhost:5000/restaurant/<int:restaurant_id>/menu/<int:menu_id>/delete' to delete item from menu of a restaurant.(Required login and permission)
9. 'https://localhost:5000/login/' to login into account.
# JSON Endpoints
1. 'https://localhost:5000/restaurant/JSON'

'''
{
  "restaurants": [
    {
      "id": 1, 
      "name": "Urban Burger"
    }
  ]
}
''' some thing like this one will appear.

2. 'https://localhost:5000/restaurant/<int:restaurant_id>/menu/JSON'

'''
{
  "MenuItems": [
    {
      "course": "Appetizer", 
      "description": "asd", 
      "id": 49, 
      "name": "Gourab", 
      "price": "12"
    }
  ]
}
'''

3. 'https://localhost:5000/restaurant/<int:restaurant_id>/menu/<int:menu_id>/JSON


'''
{
  "Menu_Item": {
    "course": "Entree", 
    "description": "Juicy grilled veggie patty with tomato mayo and lettuce", 
    "id": 1, 
    "name": "Veggie Burger", 
    "price": "$7.50"
  }
}
'''

# Troubleshout
A. If shared folder is not visiable, run vagrant reload on gitbash terminal/cmd

B. If packages or modules are not available then open vagrantfile and change/ 
paste code below to get the python3 compatiable modules and packages.
1. sudo apt-get -qqy install python3 python3-pip
2. sudo pip3 install --upgrade pip
3. sudo pip3 install flask packaging oauth2client redis passlib flask-httpauth
4. sudo pip3 install sqlalchemy flask-sqlalchemy psycopg2-binary bleach requests

C. If python3 project.py gives error that might be for dos and unix format difference. To over come install
1. run sudo apt-get install dos2unix on gitbash terminal/cmd
2. run dos2unix application.py on gitbash terminal/cmd
D. Unreachable issue may be cause due to ignoring 'https://'


