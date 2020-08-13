---
layout: post
title: A brief intro to MongoDB, installation and some queries
---

# MongoDB

  This is a brief instruction to ‘How to install **MongoDB** on Linux, how to work with it, and finally,
how to have some queries on it’. Note that my operating system is **Ubuntu 19.04** (package manager is
***apt-get*** !).
<br/>
<br/>
  There are two approaches to our purpose. One is the **Command-Line**(terminal) way and the
other one is using **MongoDB Compass** (GUI tool). We will cover both ways in this paper.

## A- Command-Line(terminal) approach :

### Step 1: Import the MongoDB repository

It`s needed to add the MongoDB repository to our package-manager(apt-get) for the purpose of
downloading

> sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 7F0CEB1

Then create a source list file for MongoDB

> echo "deb http://repo.mongodb.org/apt/ubuntu xenial/mongodb-org/3.4 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-3.4.list

Next job is to update the local package repository

> sudo apt-get update

### Step 2: Install the  MongoDB packages
Install the latest stable version of MongoDB:

> sudo apt-get install -y mongodb-org

### Step 3: Launch MongoDB as a service on Ubuntu 16.04

We need to create a unit file, which tells **systemd** how to manage a resource. Most common unit type, service, determine how to **start** or **stop** the service, **auto-start** etc.


Create a configuration file named mongodb.service in /etc/systemd/system to manage the MongoDB service.

> sudo vim /etc/systemd/system/mongodb.service

**Note**: You could use **“nano"** app instead of **“vim”** above!

Copy the following contents in the file.

<img src="../images/mongo/mongo01.png" align="center">

Update the systemd service with the command stated below:
> systemctl daemon-reload

Start the service with **systemcl**.
> sudo systemctl start mongodb

**Note**: The commands of **stop** and **restart** can be done in the same way above!


## B- MongoDB Compass(GUI tool) approach :

Referenced to [MongoDB](https://www.mongodb.com/), you can get the app via this [page](https://docs.mongodb.com/compass/master/install/). A **.deb** file would be downloaded, then you may install it with the given commands :

<img src="../images/mongo/mongo02.png" align="center">


Then press **enter** and the app will be installed soon!
The installation section finished! So we could run the MongoDB with >mongo command in our terminal,
or also run it from MongoDB Compass application.No

<img src="../images/mongo/mongo03.png" align="center">

**Now** let`s see how does it work:

First Open MongoDB app via ***>mongo*** command .
<br/>
***>show dbs*** command will show you the databases on your system
For using a specific database you can easily type ***>use DB_NAME*** (note that if the DB_NAME you`ve
entered is not valid, it would create a new database with your given name(DB_NAME)).
<br/>
You have seen in SQL we had tables, but there is no such thing in MongoDB.instead, we have
**collections** that can be defined as “an amount of data in .json format”. Via the ***>show collections***
command you can view the collections in your database. Although if you want to create a new
collection you can easily enter the below command :
